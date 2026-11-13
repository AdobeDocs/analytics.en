---
title: Create a data layer
description: Learn how a data layer supports your Analytics implementation, why Adobe recommends the Adobe Client Data Layer, and how to read data layer values with each implementation method.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Create a data layer

A data layer is a JavaScript structure on your site that exposes the data your Analytics implementation collects, such as page names, product details, and order IDs. Your site code writes to the data layer, and your implementation reads from it to set Analytics variables. Because your implementation doesn't depend on the page's HTML, you can redesign your site without breaking data collection.

## Prerequisites

[Create a solution design document](solution-design.md): It is important for your organization to align on tracking requirements. Make sure that you are prepared with a solution design document before approaching development teams in your organization. The data that your solution design requires determines what your data layer contains.

## Choose a data layer specification {#specifications}

Adobe recommends the [Adobe Client Data Layer](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview) (ACDL) for new or restructured implementations. ACDL is an open-source JavaScript library that gives your site a standard way to push data and events to a global `adobeDataLayer` array. Tags, the Web SDK, and AppMeasurement can all read from it, and Adobe Experience Manager Core Components can populate it automatically.

Your organization is free to use other specifications, such as the [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) (CEDDL), which stores data in a global `digitalData` object, or a custom specification. The most important thing is that your organization aligns on one specification that meets its needs.

The following table compares ACDL with object-based data layers such as CEDDL:

| | Adobe Client Data Layer (`adobeDataLayer`) | Object-based data layer, such as CEDDL (`digitalData`) |
| --- | --- | --- |
| How site code writes data | Pushes objects: `adobeDataLayer.push({ page: { name: "Home" } })` | Sets properties: `digitalData.page.pageInfo.pageName = "Home"` |
| How your implementation reads a value | `adobeDataLayer.getState("page.name")`, or a **Data layer computed state** data element from the Adobe Client Data Layer tag extension | `digitalData.page.pageInfo.pageName`, or a **JavaScript Variable** data element from the Core tag extension |
| How your implementation knows that data is ready | Site code pushes an event, such as `{ event: "page view" }`, and your implementation listens for it. Listeners also run for events that were pushed before they were added. | Your implementation must read the object after site code finishes populating it, for example by using a Direct Call rule. |

## Example data layer {#example}

ACDL doesn't require a specific data structure. Design the structure around your solution design document, and document it for everyone who writes to the data layer or reads from it. The examples in this guide use the following structure.

When a page loads, site code pushes the page's data and a page view event:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

When a visitor completes a purchase, site code pushes the order details and a purchase event:

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

ACDL merges every push into a single object called the computed state, which your implementation reads. Event objects tell your implementation when to read it. See [Data and the computed state](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state) and [Events](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events).

## Workflow {#workflow}

Implementing Adobe Analytics using a data layer typically follows these steps:

1. **Work with your site development team to implement a data layer**: Your site development team is primarily responsible for making sure that the data layer contains correct values. Review this page with your site development team to make sure expectations are aligned between teams. See [Install the Adobe Client Data Layer](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install).
1. **Validate your data layer using a browser console**: Open your browser's developer console, which you can do in most browsers with the `F12` key. Run `adobeDataLayer.getState()` to see the computed state, or `adobeDataLayer.getState("page.name")` to see a single value. See [Verify the installation](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install#verify).
1. **Connect the data layer to Adobe Analytics**: This step varies based on your organization's implementation method. See [Connect the data layer to Adobe Analytics](#connect).

## Connect the data layer to Adobe Analytics {#connect}

The following table shows how each implementation method reads from the Adobe Client Data Layer:

| Implementation method | How to read the data layer | More information |
| --- | --- | --- |
| Web SDK tag extension | Trigger rules with the **Data layer push** event from the Adobe Client Data Layer extension. Map data layer values to XDM fields or to the `data` object with the Web SDK **Update variable** action, then send them with the **Send event** action. | [Send Adobe Client Data Layer data with the Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk), [XDM object field mapping](../aep-edge/xdm-var-mapping.md), and [Data object field mapping](../aep-edge/data-var-mapping.md) |
| Web SDK JavaScript library | Listen for data layer events with `addEventListener()`, and set XDM or `data` fields from the data layer when you call `sendEvent`. | [Send Adobe Client Data Layer data with the Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk), [XDM object field mapping](../aep-edge/xdm-var-mapping.md), and [Data object field mapping](../aep-edge/data-var-mapping.md) |
| Analytics extension | Trigger rules with the **Data layer push** event, and create **Data layer computed state** data elements from the Adobe Client Data Layer extension. Assign the data elements to Analytics variables in the **Set Variables** action, then send the data with the **Send Beacon** action. | [Map data layer objects to data elements](../launch/layer-to-elements.md) and [Map data elements to Analytics variables](../launch/elements-to-variable.md) |
| AppMeasurement | Read values with `getState()` after ACDL loads, then call `s.t()`. | [Read the data layer with AppMeasurement](#appmeasurement) |

### Read the data layer with AppMeasurement {#appmeasurement}

ACDL adds its `getState()` method to the `adobeDataLayer` array when the library loads. To make sure that the library has loaded and that the computed state includes the latest data, read values inside an event listener:

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

The listener runs once for each `page view` event, including events that were pushed before the listener was added. The variable pages in this guide, such as [`pageName`](../vars/page-vars/pagename.md), show how to read individual values with `getState()`. Use those examples inside a listener like this one, or in the custom code editor of an Analytics extension rule that a **Data layer push** event triggers.

If your implementation sends more than one hit per page, such as in a single-page application, use [`clearVars()`](../vars/functions/clearvars.md) so that values from one hit don't persist to the next.

## Next steps

* [Map data layer objects to data elements](../launch/layer-to-elements.md): Use your site's data layer in Adobe Experience Platform tags.
* [Adobe Client Data Layer documentation](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview): Learn about every ACDL method, event, and best practice.
