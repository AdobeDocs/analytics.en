---
title: linkExternalFilters
description: Use the linkExternalFilters variable to help automatic exit link tracking.
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
---
# linkExternalFilters

AppMeasurement offers the ability to automatically track links that point outside your site. If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. The `linkExternalFilters` and [`linkInternalFilters`](linkinternalfilters.md) variables determine what links are considered internal/external.

If this variable contains a value, automatic exit link tracking behaves like an allowlist. If a link click does not match any `linkExternalFilters` values, it is not considered an exit link. The entire URL is examined against this variable. If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

>[!TIP]
>
>Only use this variable if you know exactly which domains you want to consider as exit links. Many organizations find that using `linkInternalFilters` is sufficient for their exit link tracking needs, and do not use `linkExternalFilters`.

If you use both `linkInternalFilters` and `linkExternalFilters` simultaneously, the clicked link must match `linkExternalFilters` **and** not match `linkInternalFilters` to be considered an exit link. If a clicked link matches both exit link and download link criteria, the download link type takes priority.

## Outbound Links - Track using tags in Adobe Experience Platform

The Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Outbound Links - Track] field.

Place filters that you want to always consider external in this field. Separate multiple domains by a comma without a space.

## s.linkExternalFilters in AppMeasurement and custom code editor

The `s.linkExternalFilters` variable is a string containing filters (such as domains) that you consider exit links. Separate multiple domains using a comma without spaces.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Consider the following implementation example as if it were on `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
