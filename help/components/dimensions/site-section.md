---
title: Site section
description: The name of the site section.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
---
# Site section

The 'Site section' dimension lists the names of site sections on your site. For large sites, it is helpful to group pages into sections. This dimension is useful to see the top-viewed or top-performing site sections.

This dimension is related to the [Page](page.md) and [Server](server.md) dimensions. Page is most granular, Server is least granular, and Site section is between the two.

## Populate this dimension with data

This dimension retrieves data from the [`ch` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the [`channel`](/help/implement/vars/page-vars/channel.md) variable.

## Dimension items

Dimension items include the names of site sections on your site. Your organization determines what specific dimension items you want to use. Whatever method you use, make sure it is consistent and that you record it in a [solution design document](/help/implement/prepare/solution-design.md).
