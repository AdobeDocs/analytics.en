---
title: linkLeaveQueryString
description: Allows the preservation of query strings in link tracking dimensions.
feature: Appmeasurement Implementation
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/HI9yasKxMWctqoHOlZfkvMEWo1tDa3UWuWo22Bl3jFM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# linkLeaveQueryString

AppMeasurement strips query strings from link tracking URLs by default. Use the `linkLeaveQueryString` variable to preserve query strings in link tracking dimensions.

For some exit links and download links, the important portion of the URL can be in the query string. For example, a download link such as `https://example.com/download.asp?filename=myfile.exe` contains important link information in the query string.

If link tracking information is not in URLs on your site, using this variable is not necessary. Stripping query strings from link tracking URLs helps limit the number of unique values the dimension contains.

Enabling `linkLeaveQueryString` applies to all link tracking dimensions (including custom links, exit links, and download links).

>[!TIP]
>
>This variable does not affect dimensions outside of link tracking. It only affects custom links, exit links, and download links.

## Handle link query strings using the Web SDK

Query strings are not stripped from the XDM field `web.webInteraction.URL`. If you want to strip query strings from this XDM field, you can edit it using `onBeforeEventSend`.

## Keep URL Parameters using the Adobe Analytics extension

[!UICONTROL Keep URL Parameters] is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Keep URL Parameters] checkbox.

Check this box if you want to include query strings in link tracking dimensions.

## s.linkLeaveQueryString in AppMeasurement and the Analytics extension custom code editor

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
