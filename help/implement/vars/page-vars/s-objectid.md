---
title: s_objectID
description: Help Activity Map identify unique links on your site.
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
---
# s_objectID

The `s_objectID` variable provides a unique identifier for a link. It is used to make reports in [Activity Map](/help/analyze/activity-map/activity-map.md) more accurate. If you have links on a page that frequently change, you can use the `s_objectID` variable to tell Activity Map of a unique link location so it can correctly group data as desired.

If Activity Map accuracy is crucial to your organization, Adobe recommends including the `s_objectID` variable in the `onClick` event of links on your site. See [Activity Map link tracking use cases](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) in the Analyze user guide for more information.

## Object ID using tags in Adobe Experience Platform

There is not a dedicated field in the Data Collection UI to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s_objectID in AppMeasurement and custom code editor

The `s_objectID` variable is a global variable, meaning that it operates independently of the Analytics tracking object (`s` by default). Valid values for this variable can be any string up to 100 bytes in length. If this variable is not defined, Activity Map uses the link URL as the identifier for the link.

This variable is typically set in the `onClick` event of an HTML link.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Always include the semicolon that finishes a JavaScript statement. The semicolon is required for Activity Map to function.

## Use cases

The `s_objectID` variable is valuable whenever you want increased accuracy in Activity Map reporting.

### Aggregate links from highly dynamic content

Some sites have highly dynamic content, such as news sites or retail sites with frequently rotating items. Since Activity Map uses the link URL as an identifier by default, it is difficult to understand the most-clicked areas on pages where links change frequently. If you use the `s_objectID` within these links, Activity Map understands which links can be aggregated, regardless of the URLs they point to.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Regardless of where the links point or how often you change these links, Activity Map aggregates data based on the value in `s_objectID`.

### Keep links separate on a page

Some sites have links that point to the same location in different places. For example, a link to the home page in both the header and footer on your site. Since these links have the same URL, Activity Map aggregates their data. You can separate them using the `s_objectID` variable:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Even if links point to the same URL, Activity Map can use the `s_objectID` variable to correctly distinguish them in reporting.
