---
title: Server
description: The name of the server.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
---
# Server

The 'Server' dimension typically lists the hostname of the site. For report suites that combine multiple domains or subdomains, this dimension is valuable to see which domains or subdomains perform the best.

This dimension is related to the [Page](page.md) and [Site section](site-section.md) dimensions. Page is most granular, Server is least granular, and Site section is between the two.

## Populate this dimension with data

This dimension retrieves data from the [`server` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the [`server`](/help/implement/vars/page-vars/server.md) variable.

## Dimension items

Dimension items include servers on your site. Your organization determines what specific dimension items you want to use. Some organizations use `window.location.hostname`, while others formulate a custom values. Whatever method you use, make sure it is consistent and that you record it in a [solution design document](/help/implement/prepare/solution-design.md).
