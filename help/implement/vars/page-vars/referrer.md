---
title: referrer
description: Override the automatically collected referrer for a hit.
---

# referrer

The `referrer` variable overrides the automatically collected referrer in reports. This variable is helpful in situations where the referrer might be lost, such as during redirects or temporarily forwarding the visitor to a payment processor. This variable helps populate the 'Referrer' and 'Referring Domain' dimensions.

## Referrer in Adobe Experience Platform Launch

You can set referrer either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Referrer] section.

You can set referrer to any string value, including data elements.

## s.referrer in AppMeasurement and Launch custom code editor

The `s.referrer` variable is a string containing the URL of the previous page. This variable can store a maximum of 255 bytes; values larger than 255 bytes are truncated. AppMeasurement automatically sets this variable to `document.referrer`; you do not need to set this variable unless you want to override the automatically collected value.

```js
s.referrer = "https://example.com";
```

Avoid setting this variable to non-URL values.

## Example

Many organizations deal with implementations around redirects. You can use the [`getQueryParam`](../functions/util-getqueryparam.md) utility to obtain referrer from the URL if your site accommodates it. Make sure that you URL encode any values included in the query string.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
