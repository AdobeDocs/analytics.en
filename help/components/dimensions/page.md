---
title: Page
description: The name of the page.
---

# Page

The 'Page' dimension lists the names of pages on your site. It is one of the most common dimensions used in Adobe Analytics, as it provides insight on which pages on your site perform the best.

## Populate this dimension with data

This dimension retrieves data from the [`pageName` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the `pageName` variable. If the `pageName` variable is not defined, it falls back to using the page's URL.

## Dimension values

Dimension values include the names of pages on your site. Your organization determines what specific dimension values you want to use. Some organizations directly use `document.title`, while others formulate a custom breadcrumb. Whatever method you use, make sure it is consistent and that you record it in a [solution design document](/help/implement/prepare/solution-design.md).
