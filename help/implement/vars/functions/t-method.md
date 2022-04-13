---
title: t
description: Send a page view tracking call to Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
---
# t()

The `t()` method is an important core component to Adobe Analytics. It takes all Analytics variables defined on the page, compiles them into an image request, and sends that data to Adobe data collection servers.

For example, consider the following JavaScript code:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

Running the `t()` method takes all Analytics variables defined and formulates a URL based on those variables. Some Analytics variables determine the URL of the image, while other variables determine query string parameter values.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe receives the image request, then parses the request header, URL, and query string parameters. Data collection servers then return a transparent 1x1 pixel image, invisibly displayed on your site.

## Page view tracking call using tags in Adobe Experience Platform

The Data Collection UI has a dedicated location set a page view tracking call.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the '+' icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.t()` radio button.

## s.t() method in AppMeasurement and custom code editor

Call the `s.t()` method when you want to send a tracking call to Adobe.

```js
s.t();
```

Optionally, you can use an object as an argument to override variable values. See [variable overrides](../../js/overrides.md) for more information.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Previous versions of AppMeasurement used several lines of code to call this function. The additional code historically accommodated workarounds for different browsers. Standardization and best practices in modern browsers no longer require this block of code. Only the method call `s.t()` is needed now.
