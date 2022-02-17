---
title: Dynamic variables
description: Copy variables without increasing image request length.
feature: Variables
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
---
# Dynamic variables

Dynamic variables let you copy values from one variable to another without increasing image request length. They are helpful when capturing the same data in multiple variables.

In previous versions of Analytics, image request length was important to prevent truncated data. Improvements to AppMeasurement allow much longer image request query strings, so dynamic variables are typically not needed.

Dynamic variables support query string parameters or HTTP headers in an image request. See [data collection query parameters](../../validate/query-parameters.md) for a full list of available parameters to reference. See [Standard request fields](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) on Wikipedia for a full list of available HTTP request fields to reference.

When Adobe recognizes a dynamic variable prefix, it automatically copies the query string or HTTP header value in your report suite. This action happens before any other processing, including processing rules and VISTA rules.

>[!TIP]
>
>Be mindful of maximum character limits when copying variables. For example, if copying `eVar1` to `prop1`, `prop1` can have a truncated value since it has a 100-byte limit (whereas `eVar1` has a 255-byte limit).

## Dynamic variables using tags in Adobe Experience Platform

You can use dynamic variables in any dimension field that accepts a string. Dimension items are typically set while configuring the Analytics extension (global variables) or under rules.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the desired dimension item.

Place the dynamic variable prefix in the text field, followed by the query string parameter or HTTP header that you want to reference. By default, the dynamic variable prefix is `D=`.

## Dynamic variables in AppMeasurement and custom code editor

Dynamic variables are text strings assigned to other variables. The default dynamic variable prefix is `D=`. Dynamic variables are case-sensitive.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
>Dynamic variables appear as strings when debugging your implementation. Values are copied server-side by Adobe data collection servers.
