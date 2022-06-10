---
title: Variables, functions, methods, and plug-ins overview
description: Learn what variables you can include in the data you send to Adobe to improve reporting.
keywords: appmeasurement,variables,vars,configuration,page,implementation
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
---
# Variables, functions, methods, and plug-ins overview

Analytics provides a number of variables to collect Analytics data. Variables in this section are split into several sections:

* **Page variables** are values that are typically used directly in reporting. Common page variables include `props`, `eVars`, and `events`.
* **Config variables** are settings values that help make sure the correct data reaches Adobe. Common config variables include `trackingServerSecure`, `charSet`, and `linkTrackVars`. Config variables typically do not populate dimension items.
* **Functions and methods** are pieces of code that perform a specific task when referenced. Common functions include `t()`, `tl()`, and `clearVars()`.

## Variables and implementation methods

Adobe offers multiple ways to implement Adobe Analytics. Each page offers a section on how to implement the variable using the Web SDK, using the Adobe Analytics extension, and using AppMeasurement for JavaScript.

Here is a video on configuring variables in Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/28755/?quality=12)

## Order of operations

AppMeasurement libraries published by Adobe Analytics follow a specific order when sending data to Adobe. If you execute these tasks out of order, data can be incomplete.

1. If your site uses a data layer, make sure all applicable variables are populated first. See [Data layer](../prepare/data-layer.md) for more information.
2. Use the data layer to populate Analytics variables. If you use tags in Adobe Experience Platform, this task is easily accomplished by using data elements, then assigning the data element to a variable. See [Data elements](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html).
3. Call the tracking function. Most AppMeasurement libraries use the `t()` method, however some mobile SDK's use `track()`. When the tracking function is called, all supported variables defined in the Analytics object are sent to Adobe in the form of an image request.

## Illegal characters

The following characters and strings are never allowed in JavaScript variables.

* Tab (`0x09`)
* Carriage return (`0x0D`)
* Newline (`0x0A`)
* HTML tags (e.g. `<b></b>` or `&#153`)

Some variables have additional limitations or syntax requirements. For example, the [`products`](page-vars/products.md) variable reserves semicolons and commas to delimit separate products and categories.
