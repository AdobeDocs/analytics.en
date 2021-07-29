---
title: linkLeaveQueryString
description: Allows the preservation of query strings in link tracking dimensions.
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
---
# linkLeaveQueryString

AppMeasurement strips query strings from link tracking URLs by default. Use the `linkLeaveQueryString` variable to preserve query strings in link tracking dimensions.

For some exit links and download links, the important portion of the URL can be in the query string. For example, a download link such as `https://example.com/download.asp?filename=myfile.exe` contains important link information in the query string.

If link tracking information is not in URLs on your site, using this variable is not necessary. Stripping query strings from link tracking URLs helps limit the number of unique values the dimension contains.

Enabling `linkLeaveQueryString` applies to all link tracking dimensions (including custom links, exit links, and download links).

>[!TIP]
>
>This variable does not affect dimensions outside of link tracking. It only affects custom links, exit links, and download links.

## Keep URL Parameters using tags in Adobe Experience Platform

[!UICONTROL Keep URL Parameters] is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Keep URL Parameters] checkbox.

Check this box if you want to include query strings in link tracking dimensions.

## s.linkLeaveQueryString in AppMeasurement and custom code editor

The `s.linkLeaveQueryString` variable is a boolean. Its default value is `false`.

* If this variable is set to `true`, query strings are preserved in link tracking URLs.
* If this variable is set to `false` or not defined, query strings are stripped from link tracking URLs.

```js
s.linkLeaveQueryString = true;
```

## Example

Be careful when setting this variable to true, as it can impact link tracking filters like [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md), and [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Consider the following example as if it were on `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
