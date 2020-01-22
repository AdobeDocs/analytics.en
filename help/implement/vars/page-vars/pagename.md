---
title: pageName
description: The name of the page on your site.
---

# pageName

The `pageName` variable typically stores the name of a given page. It is helpful to determine what individual pages are most popular. This variable populates the 'Page Name' dimension.

> [!NOTE] This dimension is always stripped from link tracking calls. If you want to see the page name where a link was tracked, consider copying this variable into an eVar.

If this variable is not defined on a given page tracking call, the `pageURL` variable is used instead.

## Page Name in Adobe Experience Platform Launch

You can set page name either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Page name] section.

You can set page name to any string value, including data elements.

## s.pageName in AppMeasurement and Launch custom code editor

The `s.pageName` variable is a string that typically contains the name of the page. It has a maximum value of 100 bytes; longer values are truncated. This truncation includes instances where it falls back to `pageURL` if this variable is blank.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
