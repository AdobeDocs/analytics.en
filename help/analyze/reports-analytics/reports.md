---
title: Reports
description: The dimensions and metrics that Reports & Analytics uses for each report.
---

# Reports

Each report in Reports & Analytics uses a dedicated dimension and default metric. You can change the metric in each report and add breakdowns if desired. The following lists provide what dimensions are used, and their default metric.

> [!NOTE] Your left menu can look different depending on customizations an admin in your organization has made. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

## Site Metrics

Contains reports that typically trend using a date range. Also contains unique reports, such as Recommended reports and Real-time reports.

* My recommended reports: Creates a dashboard that contains several reportlets for immediate insights.
* Key metrics: A report that allows you to trend up to five metrics at a time. Trends [page views](/help/components/metrics/page-views.md), [visits](/help/components/metrics/visits.md), and [unique visitors](/help/components/metrics/unique-visitors.md) by default.
* Page views: Trends the metric [page views](/help/components/metrics/page-views.md) over time.
* Visits: Trends the metric [visits](../../components/metrics/visits.md) over time.
* Visitors: Trends various [unique visitors](../../components/metrics/unique-visitors.md) metrics over time.
  * Unique visitors is a report that counts visitors only once for the entire selected date range.
  * Hourly unique visitors counts visitors multiple times if they visit during different hours of the selected date range.
  * Daily unique visitors counts visitors multiple times if they visit during different days of the selected date range.
  * Weekly unique visitors counts visitors multiple times if they visit during different weeks of the selected date range.
  * Monthly unique visitors counts visitors multiple times if they visit during different months of the selected date range.
  * Quarterly unique visitors counts visitors multiple times if they visit during different quarters of the selected date range. Quarters are January-March, April-June, July-September, and October-December.
  * Yearly unique visitors counts visitors multiple times if they visit during different calendar years of the selected date range.
* Time spent per visit: Uses the [time spent per visit - bucketed](../../components/dimensions/time-spent-per-visit.md) dimension with page views, visits, and unique visitors metrics.
* Time prior to event: Uses the [time prior to event](../../components/dimensions/time-prior-to-event.md) dimension with page views, visits, and unique visitors metrics.
* Purchases: Contains reports around purchase-based metrics.
  * Purchase conversion funnel reports on visits, carts, orders, revenue, and units in a funnel report.
  * Revenue: Trends the metric [revenue](../../components/metrics/revenue.md) over time.
  * Orders: Trends the metric [orders](../../components/metrics/orders.md) over time.
  * Units: Trends the metric [units](../../components/metrics/units.md) over time.
* Shopping cart: Contains reports around shopping cart metrics.
  * Cart conversion funnel reports on instances, carts, checkouts, orders, and revenue in a funnel report.
  * Carts: Trends the metric [carts](../../components/metrics/carts.md) over time.
  * Cart views: Trends the metric [cart views](../../components/metrics/cart-views.md)
  * Cart additions: Trends the metric [cart additions](../../components/metrics/cart-additions.md) over time.
  * Cart removals: Trends the metric [cart removals](../../components/metrics/cart-removals.md) over time.
  * Checkouts: Trends the metric [checkouts](../../components/metrics/checkouts.md) over time.
* Custom events: Contains all reports around custom [events](../../components/metrics/events.md) specific to your implementation.
* Bots: Shows bot-related reports.
  * Bots: Shows the bots that frequent your site the most. See [bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
  * Bot pages: Shows the pages that bots hit the most.
* Real-time: Shows certain dimensions and metrics within seconds after data collection.

## Site content

Contains reports around dimensions that typically display site content. You can apply classifications to some of these reports. Applying classifications means that a report becomes a menu that contains the source report and classification reports.

* Pages: Uses the [page](../../components/dimensions/page.md) dimension with the page views metric.
* Site section: Uses the [site section](../../components/dimensions/site-section.md) dimension with the pages views metric.
* Servers: Uses the [server](../../components/dimensions/server.md) dimension with the page views metric.
* Links: Contains reports that use link tracking.
  * Exit links: Uses the [exit link](../../components/dimensions/exit-link.md) dimension with the instances metric.
  * File downloads: Uses the [download link](../../components/dimensions/download-link.md) dimension with the instances metric.
  * Custom links: Uses the [custom link](../../components/dimensions/custom-link.md) dimension with the instances metric.
  * Pages not found: Uses the [pages not found](../../components/dimensions/pages-not-found.md) dimension with the page views metric.

## Mobile

Contains reports around legacy mobile reports. These reports base their data on the user agent string.

*