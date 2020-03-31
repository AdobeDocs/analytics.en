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
* Visits: Trends the [visits](../../components/metrics/visits.md) metric over time.
* Visitors: Trends various [unique visitors](../../components/metrics/unique-visitors.md) metrics over time.
  * Unique visitors: Counts visitors only once for the entire selected date range.
  * Hourly unique visitors: Counts visitors multiple times if they visit during different hours of the selected date range.
  * Daily unique visitors: Counts visitors multiple times if they visit during different days of the selected date range.
  * Weekly unique visitors: Counts visitors multiple times if they visit during different weeks of the selected date range.
  * Monthly unique visitors: Counts visitors multiple times if they visit during different months of the selected date range.
  * Quarterly unique visitors: Counts visitors multiple times if they visit during different quarters of the selected date range. Quarters are January-March, April-June, July-September, and October-December.
  * Yearly unique visitors: Counts visitors multiple times if they visit during different calendar years of the selected date range.
* Time spent per visit: Uses the [time spent per visit - bucketed](../../components/dimensions/time-spent-per-visit.md) dimension with [page views](../../components/metrics/page-views.md), [visits](../../components/metrics/visits.md), and [unique visitors](../../components/metrics/unique-visitors.md) metrics.
* Time prior to event: Uses the [time prior to event](../../components/dimensions/time-prior-to-event.md) dimension with [page views](../../components/metrics/page-views.md), [visits](../../components/metrics/visits.md), and [unique visitors](../../components/metrics/unique-visitors.md) metrics.
* Purchases: Contains reports around purchase-based metrics.
  * Purchase conversion funnel: Report on [visits](../../components/metrics/visits.md), [carts](../../components/metrics/carts.md), [orders](../../components/metrics/orders.md), [revenue](../../components/metrics/revenue.md), and [units](../../components/metrics/units.md) in a funnel report. A similar visualization is achieved in Analysis Workspace using the [fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
  * Revenue: Trends the metric [revenue](../../components/metrics/revenue.md) over time.
  * Orders: Trends the metric [orders](../../components/metrics/orders.md) over time.
  * Units: Trends the metric [units](../../components/metrics/units.md) over time.
* Shopping cart: Contains reports around shopping cart metrics.
  * Cart conversion funnel: Reports [instances](../../components/metrics/instances.md), [carts](../../components/metrics/carts.md), [checkouts](../../components/metrics/checkouts.md), [orders](../../components/metrics/orders.md), and [revenue](../../components/metrics/revenue.md) in a funnel report.
  * Carts: Trends the metric [carts](../../components/metrics/carts.md) over time.
  * Cart views: Trends the metric [cart views](../../components/metrics/cart-views.md) over time.
  * Cart additions: Trends the metric [cart additions](../../components/metrics/cart-additions.md) over time.
  * Cart removals: Trends the metric [cart removals](../../components/metrics/cart-removals.md) over time.
  * Checkouts: Trends the metric [checkouts](../../components/metrics/checkouts.md) over time.
* Custom events: Contains all reports around custom [events](../../components/metrics/events.md) specific to your implementation.
* Bots: Shows bot-related reports.
  * Bots: Shows the bots that frequent your site the most. See [bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
  * Bot pages: Shows the pages that bots hit the most.
* Real-time: Shows certain dimensions and metrics within seconds after data collection. See [real-time reports](../../components/c-real-time-reporting/realtime.md) for more information.

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

Contains reports around legacy mobile reports. These reports base their data on the user agent string. They use various [mobile dimensions](../../components/dimensions/mobile-dimensions.md) for their respective reports.

* Devices: Uses the [mobile device](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Device type: Uses the [mobile device type](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Manufacturer: Uses the [mobile manufacturer](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Screen size: Uses the [mobile screen size](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Screen height: Uses the [mobile screen height](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Screen width: Uses the [mobile screen width](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Cookie support: Uses the [mobile cookie support](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Image support: Uses the [mobile image support](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Color depth: Uses the [mobile color depth](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Audio support: Uses the [mobile audio support](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Video support: Uses the [mobile video support](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.
* Operating system (deprecated): Uses the [mobile operating system (deprecated)](../../components/dimensions/mobile-dimensions.md) dimension with the page views metric.

## Paths

Contains reports that allow you to see pathing data for visitors.

* Next page flow: Uses a flow report on the top page dimension value with the path views metric. Path views are similar to [instances](../../components/metrics/instances.md). You can change the reported dimension value. A similar report in Analysis Workspace is available using a [flow visualization](../analysis-workspace/visualizations/c-flow/flow.md).
* Next page: Takes the top page dimension value and shows you the next pages visitors went to with the instances metric.
* Previous page flow: Uses a flow report on the top page dimension value with the path views metric. A similar report in Analysis Workspace is available using a [flow visualization](../analysis-workspace/visualizations/c-flow/flow.md).
* Previous page: Takes the top page dimension value and shows you the previous pages visitors came from with the instances metric.
* Fallout: Allows you to select page dimension values in steps, and shows the proportion of people who did and did not follow that path. A similar report in Analysis Workspace is available using a [fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Full paths: Shows individual paths as dimension values with the [visits](../../components/metrics/visits.md) metric.
* PathFinder: Provides multiple types of reports that let you analyze paths using the path views metric.
* Path length: Uses the [visit depth](../../components/dimensions/visit-depth.md) dimension with the [visits](../../components/metrics/visits.md) metric.
* Page Analysis
  * Page summary: Takes the top page dimension value and shows a trended view using the page views metric. Also shows entry points, previous pages, exit points, and next pages for that top page dimension value.
  * Reloads: Uses the page dimension with the [reloads](../../components/metrics/reloads.md) metric.
  * Time spent on page: Uses the [time spent on page - bucketed](../../components/dimensions/time-spent-on-page.md) dimension with the instances metric.
  * Clicks to page: Takes the top page dimension value and shows the number of clicks it took to get to that page in a given visit. Uses the visits metric.
* Entries and exits
  * Entry pages: Uses the [entry pages](../../components/dimensions/entry-dimensions.md) dimension with the page views metric.
  * Original entry pages: Uses the entry page original dimension with the page views metric.
  * Single page visits: Uses the page dimension with the visits metric. It acts similar to a report using the default single page visits segment.
  * Exit pages: Uses the [exit pages](../../components/dimensions/exit-dimensions.md) dimension with the page views metric.

> [!NOTE] Other reports can appear in this folder. They are other dimensions, such as props, where you have enabled pathing under report suite settings.

## Traffic sources

Contains report that give insight to where visitors came from before arriving to your site. These reports do not work correctly unless you correctly set [internal URL filters](../../admin/admin/internal-url-filter-admin.md) under report suite settings.

* Search keywords - all: Uses the [search keyword](../../components/dimensions/search-keyword.md) dimension with the page views metric.
* Search keywords - paid: Uses the [search keyword - paid](../../components/dimensions/search-keyword.md) dimension with the page views metric.
* Search keywords - natural: Uses the [search keyword - natural](../../components/dimensions/search-keyword.md) dimension with the page views metric
* Search engines - all: Uses the [search engine](../../components/dimensions/search-engine.md) dimension with the page views metric.
* Search engines - paid: Uses the [search engine - paid](../../components/dimensions/search-engine.md) dimension with the page views metric.
* Search engines - natural: Uses the [search engine - natural](../../components/dimensions/search-engine.md) dimension with the page views metric.
* All search page ranking: Uses the [all search page rank](../../components/dimensions/all-search-page-rank.md) dimension with the page views metric.
* Referring domains: Uses the [referring domain](../../components/dimensions/referring-domain.md) dimension with the page views metric
* Original referring domains: Uses the [original referring domain](../../components/dimensions/original-referring-domain.md) dimension with the page views metric
* Referrers: Uses the [referrer](../../components/dimensions/referrer.md) dimension with the page views metric.
* Referrer types: Uses the [referrer type](../../components/dimensions/referrer-type.md) dimension with the page views metric.

## Campaigns

Contains reports primarily around the [tracking code](../../components/dimensions/tracking-code.md) dimension.

* Campaign conversion funnel: Reports click-throughs, checkouts, orders, and revenue in a funnel report. The click-throughs metric is similar to the [instances](../../components/metrics/instances.md) metric in context of the [tracking code](../../components/dimensions/tracking-code.md) dimension. A similar visualization is achieved in Analysis Workspace using the [fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Tracking code: Uses the [tracking code](../../components/dimensions/tracking-code.md) dimension with the [page views](../../components/metrics/page-views.md) metric.

## Products

Contains reports around the [product](dimensions/../../../components/dimensions/product.md) dimension.

* Products conversion funnel: Reports [product views](../../components/metrics/product-views.md), [cart additions](../../components/metrics/cart-additions.md), [checkouts](../../components/metrics/checkouts.md), [orders](../../components/metrics/orders.md), [units](../../components/metrics/units.md), and [revenue](../../components/metrics/revenue.md) in a funnel report. A similar visualization is achieved in Analysis Workspace using the [fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Products: Uses the [products](../../components/dimensions/product.md) dimension with the [revenue](../../components/metrics/revenue.md) and [visits](../../components/metrics/visits.md) metrics.
* Cross sell: Shows products commonly sold together with the [revenue](../../components/metrics/revenue.md) and [visits](../../components/metrics/visits.md) metrics.
* Categories: Shows the [category](../../components/dimensions/category.md) dimension with the [revenue](../../components/metrics/revenue.md) and [visits](../../components/metrics/visits.md) metrics.

## Visitor retention

Contains reports around visitors that return to your site.

* Return frequency: Uses the [return frequency](../../components/dimensions/return-frequency.md) dimension with the [page views](../../components/metrics/page-views.md) metric.
* Return visits: Trends the [visits](../../components/metrics/visits.md) metric over time with the Adobe-provided return visits segment applied.
* Visit number: 
* Sales cycle
  * Customer loyalty:
  * Days before first purchase
  * Days since last purchase
  * Daily unique customers
  * Weekly unique customers
  * Monthly unique customers
  * Quarterly unique customers
  * Yearly unique customers

## Visitor profile