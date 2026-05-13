---
title: Variables, functions, methods, and plug-ins overview
description: Learn what variables you can include in the data you send to Adobe to improve reporting.
keywords: appmeasurement,variables,vars,configuration,page,implementation
feature: Appmeasurement Implementation
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
role: Admin, Developer
TQID: https://experienceleague.adobe.com/J3bg65cq6Qjbv-Y-2sBaTmVHHniMpwudiM-YOM8VAhk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Variables, functions, methods, and plug-ins overview

Analytics provides a number of variables to collect Analytics data. Variables in this section are split into several sections:

* **Page variables** are values that are typically used directly in reporting. Common page variables include `props`, `eVars`, and `events`.
* **Config variables** are settings values that help make sure the correct data reaches Adobe. Common config variables include `trackingServerSecure`, `charSet`, and `linkTrackVars`. Config variables typically do not populate dimension items.
* **Functions and methods** are pieces of code that perform a specific task when referenced. Common functions include `t()`, `tl()`, and `clearVars()`.

## Variables and implementation methods

Adobe offers multiple ways to implement Adobe Analytics. Each page offers a section on how to implement the variable using the Web SDK, using the Adobe Analytics extension, and using AppMeasurement for JavaScript.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring variables](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/manage-report-suites/configuring-variables-in-the-admin-console){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Order of operations

AppMeasurement libraries published by Adobe Analytics follow a specific order when sending data to Adobe. If you execute these tasks out of order, data can be incomplete.

1. If your site uses a data layer, make sure all applicable variables are populated first. For example, you populate `adobeDataLayer.page.title` with the page title. See [Data layer](../prepare/data-layer.md) for more information. 
2. Use the data layer to populate Analytics variables. <br/>If you use tags in Adobe Experience Platform, this task is accomplished by using data elements in between. Data elements are populated with values from the data layer. For example data element `Page Title` gets the value from data layer variable `adobeDataLayer.page.title`. <br/>Then you can use the data element to populate Analytics variables. For example `eVar4` gets the value from data element `Page Title`. <br/>See for more information [Data elements](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html), [Map data layer objects to data elements](../launch/layer-to-elements.md), and [Map tag data elements to Analytics variables](../launch/elements-to-variable.md)
3. Finally, call the tracking function. Most AppMeasurement libraries use the `t()` method, however some mobile SDK's use `track()`. When the tracking function is called, all supported variables defined in the Analytics object are sent to Adobe in the form of an image request.

## Illegal characters

The following characters and strings are never allowed in JavaScript variables.

* Tab (`0x09`)
* Carriage return (`0x0D`)
* Newline (`0x0A`)
* HTML tags (e.g. `<b></b>` or `&#153`)

Some variables have additional limitations or syntax requirements. For example, the [`products`](page-vars/products.md) variable reserves semicolons and commas to delimit separate products and categories.
