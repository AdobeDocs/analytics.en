---
title: Create a data layer
description: Learn what a data layer is in your Analytics implementation, and how it can be used to map variables in Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
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

A data layer is a framework of JavaScript objects on your site that contain the variable values used in your Analytics implementation. It allows greater control and easier maintenance when assigning values to Analytics variables.

## Prerequisites

[Create a solution design document](solution-design.md) - It is important for your organization to align on tracking requirements. Make sure that you are prepared with a solution design document before approaching development teams in your organization.

## Workflow

Implementing Adobe Analytics using a data layer typically follows these steps:

1. **Work with your site development team to implement a data layer**: Your site development team is primarily responsible for making sure the data layer object populates with correct values. Review this page with your site development team to make sure expectations are aligned between teams.

   >[!NOTE]
   >
   >Following Adobe's recommended data layer specifications is optional. If you already have a data layer, or otherwise choose not to follow Adobe's specifications, make sure that your organization aligns on what specification to follow.

1. **Validate your data layer using a browser console**: Once a data layer is created, you can validate that it is working using any browser's developer console. You can open the developer console in most browsers using the `F12` key. An example variable value would be `adobeDataLayer.page.title`.
1. **Use Adobe Experience Platform Data Collection to map data layer objects to data elements**: This step varies based on your organization's implementation method:
   * **If using the Web SDK**: Map the desired data layer objects to the desired XDM fields in Adobe Experience Platform Edge. See [Analytics XDM variable mapping](../aep-edge/xdm-var-mapping.md) to determine the desired data layer mapping.
   * **If using the Analytics extension**: Create data elements under Tags in Adobe Experience Platform Data Collection, and assign them to the desired data layer objects. Then within the Analytics extension, assign each data element to the appropriate Analytics variable.

## Specifications

Adobe recommends using the [Adobe Client Data Layer](https://github.com/adobe/adobe-client-data-layer/wiki) for new or restructured implementations.

Your organization is free to use other data layer specifications, such as the [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf), or another custom specification entirely. Aligning to a consistent data layer that meets your organization's needs is the most important.

Data layers are extensible; if you have requirements specific to your organization, you can include objects in your data layer to accommodate those needs.

## Setting data layer values

Data layers typically generate server-side, referencing the same objects used to build the site content. Establish the site's data layer based on tracking requirements set in your organization's [solution design document](solution-design.md).

## Next steps

[Map data layer objects to data elements](../launch/layer-to-elements.md): Use your site's data layer in Adobe Experience Platform.
