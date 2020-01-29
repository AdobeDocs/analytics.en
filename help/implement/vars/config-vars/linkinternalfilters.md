---
title: linkInternalFilters
description: Use the linkInternalFilters variable to help automatic exit link tracking.
---

# linkInternalFilters

AppMeasurement offers the ability to automatically track links that point outside your site. If `trackExternalLinks` is `true`, an image request is sent to Adobe right as a visitor clicks a link to leave your site. The `linkTrackExternalFilters` and `linkTrackInternalFilters` variables determine what links are considered internal/external.

If this variable contains a value, automatic exit link tracking behaves in a blacklist-like manner. If a link click does not match any `linkInternalFilters` values, it is considered an exit link. The entire URL is examined against this variable. If `linkLeaveQueryString` is `true`, the query string is also examined.

If you use both `linkInternalFilters` and `linkExternalFilters` simultaneously, the clicked link must match `linkExternalFilters` **and** not match `linkInternalFilters` to be considered an exit link. If a clicked link matches both exit link and download link criteria, the download link type takes priority.

> [!NOTE] `linkInternalFilters` and Internal URL filters are separate features that fulfill separate purposes. The `linkInternalFilters` variable works specifically for exit link tracking. Internal URL filters are an Admin setting that help with traffic sources dimensions like Referring Domain. See [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) in the Admin user guide.

## Outbound Links - Never Track in Adobe Experience Platform Launch

The Never Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Outbound Links - Never Track] field.

Place filters that you want to never be tracked as exit links in this field. Separate multiple domains by a comma without a space.

## s.linkInternalFilters in AppMeasurement and Launch custom code editor

The `s.linkInternalFilters` variable is a string containing filters (such as domains) that you consider internal to your site. Separate multiple filters using a comma without spaces.

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

Consider the following implementation example as if it were on `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
