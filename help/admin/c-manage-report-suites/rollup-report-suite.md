---
description: Rollup report suites aggregate data from multiple child report suites and display them in a summarized data set.
seo-description: Rollup report suites aggregate data from multiple child report suites and display them in a summarized data set.
seo-title: Rollup and global report suites
solution: Analytics
title: Rollup and global report suites
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
---

# Rollup and global report suites

Rollup report suites aggregate data from multiple child report suites and display them in a summarized data set.

Not to be mistaken with global report suites, rollups provide a convenient place to see summed totals such as Page Views, Revenue, or Technology metrics. Rollups are frequently used because they do not require additional implementation.

## Definitions of Report Suite Types {#section_E51E03E3917040278600A7E9638A91C7}

**Global report suite**: Implementation is altered to send image requests across domains into a single global report suite, in addition to individual report suites.

**Rollup report suite**: Created in Admin Tools. Takes the sum of each metric at the end of every day.

* Rollups are free to use and do not increment any server calls.
* Rollups provide total data, but do not report individual values in reports. For example, eVar1 values are not included, but its aggregate total can be.
* Data is not deduplicated when combining data across report suites. A single user can touch three different report suites in a single day, and would appear as three daily unique visitors in the rollup.
* Rollup aggregation happens on a nightly basis.
* When adding a report suite to an existing rollup, historical data is not included in the rollup.
* Rollup report suites have limited reporting capabilities. For example, unique visitor counts are added across report suites. If the same person visits two separate report suites, a rollup lists that person as two visitors, whereas a standard global report suite shows one visitor.
* All child report suites must have data in them in order for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to those report suites.
* Rollup report suites are limited to a maximum of 40 child report suites.
* Rollup report suites are limited to a maximum of 100 events.
* Data contained in Rollup report suites does not support subrelations, segments, or any metrics that were introduced in marketing reports.
* The Pages report is not available in rollup report suites. It is replaced by the Most Popular Sites report, which reports on metrics at the child-suite level.

## Rollup vs. Global Report Suites {#section_7B3703DC7ABF4B9EA9DF02A54592CAD0}

**Server calls**: Global report suites increment secondary server calls, while rollups do not make any server calls whatsoever.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require an additional report suite ID be placed in the s_code.js file.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Global report suites can attribute credit to conversion variables between report suites, as well as provide pathing across report suites. Rollups have no way to communicate between report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide additional information on ALL reports implemented; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups are not supported in data warehouse or ad hoc analysis. Marketing reports are limited to 40 child report suites. Global report suites can be used across all products, and can have an unlimited number of child report suites.

## Which Report Suite Type Do I Want to Implement? {#section_868066B9604B49BABBF84074BA5E9C71}

When choosing whether to use rollups or global report suites, consider the following:

* Is the number of server calls critical to my organization? If keeping server calls limited is important, consider using rollups. Global report suites almost double the number of server calls made.
* Does reporting a high-level total of traffic across all suites suffice? If deduplicated visitors are a requirement, consider implementing a global report suite.
* Are pathing and conversion/success events across domains important? If cross-site campaigns are heavily used, consider implementing a global report suite.
* Is viewing total site data time-sensitive? Individual report suites still report near real time. If seeing report suite totals the next day is adequate, rollups are recommended.
* Is there a large amount of actionable historical data? Global report suites cannot report retroactively - rollups are recommended if historical data is important.
* Is data warehouse and ad hoc analysis essential to supplement reporting? If so, a global report suite is recommended.

Neither choice affects individual report suites. Carefully consider the pros and cons before determining which your organization prefers.
