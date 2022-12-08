---
title: linkInternalFilters
description: Use the linkInternalFilters variable to help automatic exit link tracking.
feature: Variables
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
---
# linkInternalFilters

AppMeasurement offers the ability to automatically track links that point outside your site. If [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) or [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. The [`linkExternalFilters`](linkexternalfilters.md) and `linkInternalFilters` variables determine what links are considered internal/external.

If this variable contains a value, automatic exit link tracking behaves like a block list. If a link click does not match any `linkInternalFilters` values, it is considered an exit link. The entire URL is examined against this variable. If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

If you use both `linkInternalFilters` and `linkExternalFilters` simultaneously, the clicked link must match `linkExternalFilters` **and** not match `linkInternalFilters` to be considered an exit link. If a clicked link matches both exit link and download link criteria, the download link type takes priority.

Activity map uses this variable to help determine what links are internal to your site. Adobe recommends setting this variable for implementations that use Activity map.

>[!NOTE]
>
>`linkInternalFilters` and [Internal URL filters](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) are separate features that fulfill separate purposes. The `linkInternalFilters` variable works specifically for exit link tracking. Internal URL filters are an Admin setting that help with traffic sources dimensions like Referring Domain.

## Exit links in the Web SDK

Links automatically qualify as an exit link if the link target domain differs from the current `window.location.hostname`. The Web SDK does not offer any configuration variables to modify automatic exit link detection. If you need to customize the domains that qualify as an exit link, you can use custom logic in the `onBeforeEventSend` callback.

See [Automatic link tracking](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) in the Web SDK documentation for more information.

## Outbound Links - Never Track using the Adobe Analytics extension

The Never Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Outbound Links - Never Track] field.

Place filters that you want to never be tracked as exit links in this field. Separate multiple domains by a comma without a space.

## s.linkInternalFilters in AppMeasurement and the Analytics extension custom code editor

The `s.linkInternalFilters` variable is a string containing filters (such as domains) that you consider internal to your site. Separate multiple filters using a comma without spaces.

```js
s.linkInternalFilters = "example.com,example.net";
```

Consider the following implementation example as if it were on `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
