---
title: Exit Links
description: Report on the most common links people click to leave your site.
---

# Exit Links

Shows the most common links people are click to leave your site. These links typically point to partner or affiliate sites; however, they can be any location where you have an external link. You can use this report to view the most popular affiliate links, or to assist in validating the number of referrals that your partners' state you provide.

There are several requirements that must be met in order for this page to populate correctly:
* If using manual custom link tracking, a `tl()` request must be fired with the middle parameter set to `e`.
* If using automatic custom link tracking, all requirements must be met:
  * The [trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) variable must be enabled.
  * The link the user clicked on must not match any values within the [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) variable.
  * If the [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) variable exists, the external link must match at least one of the values set in this variable.
* If any of the above requirements are not met, the hit does not populate this report.
* As with all custom link tracking hits, the [pageName](/help/implement/vars/page-vars/pagename.md) variable is stripped from the image request to prevent inflation to the page views metric.
* You can view this report in trended and ranked formats.
* This report can use a search filter to locate specific line items.
* You can create [breakdowns](/help/analyze/reports-analytics/reports-customize/breakdowns.md) with any other variable.
