---
title: Page
description: The name of the page.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
---
# Page

The 'Page' dimension lists the names of pages on your site. It is one of the most common dimensions used in Adobe Analytics, as it provides insight on which pages on your site perform the best.

This dimension is related to the [Site section](site-section.md) and [Server](server.md) dimensions. Page is most granular, Server is least granular, and Site section is between the two.

## Populate this dimension with data

This dimension retrieves data from the [`pageName` query string](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [Link tracking calls (`tl()`)](/help/implement/vars/functions/tl-method.md) always strip this dimension, even if the `pageName` query string exists.

AppMeasurement collects this data using the [`pageName`](/help/implement/vars/page-vars/pagename.md) variable. If the `pageName` variable is not defined, it falls back to using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Dimension items

Dimension items include the names of pages on your site. Your organization determines what specific dimension items you want to use. Some organizations directly use `document.title`, while others formulate a custom breadcrumb. Whatever method you use, make sure it is consistent and that you record it in a [solution design document](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>In Reports & Analytics, conversion metrics use linear attribution for this dimension. For example, revenue is split between all pages viewed in a visit before a `purchase` event. Analysis Workspace uses last attribution by default, with the option to use any attribution model.
