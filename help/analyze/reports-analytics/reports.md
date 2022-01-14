---
title: Reports
description: The dimensions and metrics that Reports & Analytics uses for each report.
feature: Reports & Analytics Basics
role: User, Admin
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
---
# Reports

Each report in Reports & Analytics uses a dedicated dimension and default metric. You can change the metric in each report and add breakdowns if desired. The following lists provide what dimension is used in each report.

>[!NOTE]
>
>Your reports menu can look different depending on customizations an admin in your organization has made. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

>[!IMPORTANT]
>Effective **December 31, 2023**, Adobe intends to discontinue Reports & Analytics and its accompanying reports and features. At that time, Reports & Analytics and all of its reports and schedules will stop working. The reports, visualizations and underlying technology that power Reports & Analytics no longer meet Adobe’s technology standards. Most Reports & Analytics features are available within Analysis Workspace. Since the release of Analysis Workspace in 2015, Reports & Analytics functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. This notice explains the end-of-life process.

## Site Metrics

Contains reports that typically trend using a date range. Also contains unique reports, such as Recommended reports and Real-time reports.

* My recommended reports: Creates a dashboard that contains several reportlets for immediate insights.
* Key metrics: A report that allows you to trend up to five metrics at a time. Trends [Page views](/help/components/metrics/page-views.md), [Visits](/help/components/metrics/visits.md), and [Unique visitors](/help/components/metrics/unique-visitors.md) by default.
* Page views: Trends the [Page views](/help/components/metrics/page-views.md) metric over time.
* Visits: Trends the [Visits](/help/components/metrics/visits.md) metric over time.
* Visitors: Trends various [Unique visitors](/help/components/metrics/unique-visitors.md) metrics over time.
  * Unique visitors: Counts visitors only once for the entire selected date range.
  * Hourly unique visitors: Counts visitors multiple times if they visit during different hours of the selected date range.
  * Daily unique visitors: Counts visitors multiple times if they visit during different days of the selected date range.
  * Weekly unique visitors: Counts visitors multiple times if they visit during different weeks of the selected date range.
  * Monthly unique visitors: Counts visitors multiple times if they visit during different months of the selected date range.
  * Quarterly unique visitors: Counts visitors multiple times if they visit during different quarters of the selected date range. Quarters are January-March, April-June, July-September, and October-December.
  * Yearly unique visitors: Counts visitors multiple times if they visit during different calendar years of the selected date range.
* Time spent per visit: Uses the [Time spent per visit - bucketed](/help/components/dimensions/time-spent-per-visit.md) dimension.
* Time prior to event: Uses the [Time prior to event](/help/components/dimensions/time-prior-to-event.md) dimension.
* Purchases: Contains reports around purchase-based metrics.
  * Purchase conversion funnel: Report on [Visits](/help/components/metrics/visits.md), [Carts](/help/components/metrics/carts.md), [Orders](/help/components/metrics/orders.md), [Revenue](/help/components/metrics/revenue.md), and [Units](/help/components/metrics/units.md) in a funnel report. A similar visualization is achieved in Analysis Workspace using the [Fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
  * Revenue: Trends the metric [Revenue](/help/components/metrics/revenue.md) over time.
  * Orders: Trends the metric [Orders](/help/components/metrics/orders.md) over time.
  * Units: Trends the metric [Units](/help/components/metrics/units.md) over time.
* Shopping cart: Contains reports around shopping cart metrics.
  * Cart conversion funnel: Reports [Instances](/help/components/metrics/instances.md), [Carts](/help/components/metrics/carts.md), [Checkouts](/help/components/metrics/checkouts.md), [Orders](/help/components/metrics/orders.md), and [Revenue](/help/components/metrics/revenue.md) in a funnel report.
  * Carts: Trends the metric [Carts](/help/components/metrics/carts.md) over time.
  * Cart views: Trends the metric [Cart views](/help/components/metrics/cart-views.md) over time.
  * Cart additions: Trends the metric [Cart additions](/help/components/metrics/cart-additions.md) over time.
  * Cart removals: Trends the metric [Cart removals](/help/components/metrics/cart-removals.md) over time.
  * Checkouts: Trends the metric [Checkouts](/help/components/metrics/checkouts.md) over time.
* Custom events: Contains all reports around custom [Events](/help/components/metrics/custom-events.md) specific to your implementation.
* Bots: Shows bot-related reports.
  * Bots: Shows the bots that frequent your site the most. See [Bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
  * Bot pages: Shows the pages that bots hit the most.
* Real-time: Shows certain dimensions and metrics within seconds after data collection. See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## Site content

Contains reports around dimensions that typically display site content. You can apply classifications to some of these reports. Applying classifications means that a report becomes a menu that contains the source report and classification reports.

* Pages: Uses the [Page](/help/components/dimensions/page.md) dimension.
* Site section: Uses the [Site section](/help/components/dimensions/site-section.md) dimension.
* Servers: Uses the [Server](/help/components/dimensions/server.md) dimension.
* Links: Contains reports that use link tracking.
  * Exit links: Uses the [Exit link](/help/components/dimensions/exit-link.md) dimension.
  * File downloads: Uses the [Download link](/help/components/dimensions/download-link.md) dimension.
  * Custom links: Uses the [Custom link](/help/components/dimensions/custom-link.md) dimension.
  * Pages not found: Uses the [Pages not found](/help/components/dimensions/pages-not-found.md) dimension.

## Mobile

Contains reports around legacy mobile reports. These reports base their data on the user agent string. They use various [mobile dimensions](/help/components/dimensions/mobile-dimensions.md) for their respective reports.

* Devices: Uses the [Mobile device](/help/components/dimensions/mobile-dimensions.md) dimension.
* Device type: Uses the [Mobile device type](/help/components/dimensions/mobile-dimensions.md) dimension.
* Manufacturer: Uses the [Mobile manufacturer](/help/components/dimensions/mobile-dimensions.md) dimension.
* Screen size: Uses the [Mobile screen size](/help/components/dimensions/mobile-dimensions.md) dimension.
* Screen height: Uses the [Mobile screen height](/help/components/dimensions/mobile-dimensions.md) dimension.
* Screen width: Uses the [Mobile screen width](/help/components/dimensions/mobile-dimensions.md) dimension.
* Cookie support: Uses the [Mobile cookie support](/help/components/dimensions/mobile-dimensions.md) dimension.
* Image support: Uses the [Mobile image support](/help/components/dimensions/mobile-dimensions.md) dimension.
* Color depth: Uses the [Mobile color depth](/help/components/dimensions/mobile-dimensions.md) dimension.
* Audio support: Uses the [Mobile audio support](/help/components/dimensions/mobile-dimensions.md) dimension.
* Video support: Uses the [Mobile video support](/help/components/dimensions/mobile-dimensions.md) dimension.
* Operating system (deprecated): Uses the [Mobile operating system (deprecated)](/help/components/dimensions/mobile-dimensions.md) dimension.

## Paths

Contains reports that allow you to see pathing data for visitors.

* Next page flow: Uses a flow report on the top page dimension item. Path views are similar to [Instances](/help/components/metrics/instances.md). You can change the reported dimension item. A similar report in Analysis Workspace is available using a [Flow visualization](../analysis-workspace/visualizations/c-flow/flow.md).
* Next page: Takes the top page dimension item and shows you the next pages visitors went to.
* Previous page flow: Uses a flow report on the top page dimension item A similar report in Analysis Workspace is available using a [Flow visualization](../analysis-workspace/visualizations/c-flow/flow.md).
* Previous page: Takes the top page dimension item and shows you the previous pages visitors came from.
* Fallout: Allows you to select page dimension items in steps, and shows the proportion of people who did and did not follow that path. A similar report in Analysis Workspace is available using a [Fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Full paths: Shows individual paths as dimension items. Retired in Analysis Workspace; use the [Flow visualization](../analysis-workspace/visualizations/c-flow/flow.md) instead.
* PathFinder: Provides multiple types of reports that let you analyze paths (retired in Analysis Workspace).
* Path length: Uses the [Visit depth](/help/components/dimensions/visit-depth.md) dimension.
* Page Analysis
  * Page summary: Takes the top page dimension item and shows a trended view. Also shows entry points, previous pages, exit points, and next pages for that top page dimension item.
  * Reloads: Uses the [Page](/help/components/dimensions/page.md) dimension with the [Reloads](/help/components/metrics/reloads.md) metric.
  * Time spent on page: Uses the [Time spent on page - bucketed](/help/components/dimensions/time-spent-on-page.md) dimension.
  * Clicks to page: Takes the top page dimension item and shows the number of clicks it took to get to that page in a given visit.
* Entries and exits
  * Entry pages: Uses the [Entry pages](/help/components/dimensions/entry-dimensions.md) dimension.
  * Original entry pages: Uses the [Entry page original](/help/components/dimensions/entry-dimensions.md) dimension.
  * Single page visits: Uses the [Page](/help/components/dimensions/page.md) dimension with the Adobe-provided 'Single page visits' segment applied.
  * Exit pages: Uses the [Exit pages](/help/components/dimensions/exit-dimensions.md) dimension.

>[!NOTE]
>
>Other reports can appear in this folder. They are other dimensions, such as props, where you have [pathing enabled](../../admin/admin/c-traffic-variables/traffic-var.md) under report suite settings.

## Traffic sources

Contains report that give insight to where visitors came from before arriving to your site. These reports do not work correctly unless you correctly set [Internal URL filters](../../admin/admin/internal-url-filter-admin.md) under report suite settings.

* Search keywords - all: Uses the [Search keyword](/help/components/dimensions/search-keyword.md) dimension.
* Search keywords - paid: Uses the [Search keyword - paid](/help/components/dimensions/search-keyword.md) dimension.
* Search keywords - natural: Uses the [Search keyword - natural](/help/components/dimensions/search-keyword.md) dimension
* Search engines - all: Uses the [Search engine](/help/components/dimensions/search-engine.md) dimension.
* Search engines - paid: Uses the [Search engine - paid](/help/components/dimensions/search-engine.md) dimension.
* Search engines - natural: Uses the [Search engine - natural](/help/components/dimensions/search-engine.md) dimension.
* All search page ranking: Uses the [All search page rank](/help/components/dimensions/all-search-page-rank.md) dimension.
* Referring domains: Uses the [Referring domain](/help/components/dimensions/referring-domain.md) dimension
* Original referring domains: Uses the [Original referring domain](/help/components/dimensions/original-referring-domain.md) dimension
* Referrers: Uses the [Referrer](/help/components/dimensions/referrer.md) dimension.
* Referrer types: Uses the [Referrer type](/help/components/dimensions/referrer-type.md) dimension.

## Campaigns

Contains reports primarily around the [Tracking code](/help/components/dimensions/tracking-code.md) dimension.

* Campaign conversion funnel: Reports click-throughs, [Checkouts](/help/components/metrics/checkouts.md), [Orders](/help/components/metrics/orders.md), and [Revenue](/help/components/metrics/revenue.md) in a funnel report. The click-throughs metric is similar to the [Instances](/help/components/metrics/instances.md) metric in context of the [Tracking code](/help/components/dimensions/tracking-code.md) dimension. A similar visualization is achieved in Analysis Workspace using the [Fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Tracking code: Uses the [Tracking code](/help/components/dimensions/tracking-code.md) dimension.

## Products

Contains reports primarily around the [Product](/help/components/dimensions/product.md) dimension.

* Products conversion funnel: Reports [Product views](/help/components/metrics/product-views.md), [Cart additions](/help/components/metrics/cart-additions.md), [Checkouts](/help/components/metrics/checkouts.md), [Orders](/help/components/metrics/orders.md), [Units](/help/components/metrics/units.md), and [Revenue](/help/components/metrics/revenue.md) in a funnel report. A similar visualization is achieved in Analysis Workspace using the [Fallout visualization](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Products: Uses the [Products](/help/components/dimensions/product.md) dimension.
* Cross sell: Shows products commonly sold together (retired in Analysis Workspace).
* Categories: Uses the [Category](/help/components/dimensions/category.md) dimension.

## Visitor retention

Contains reports around visitors that return to your site.

* Return frequency: Uses the [Return frequency](/help/components/dimensions/return-frequency.md) dimension.
* Return visits: Trends the [Visits](/help/components/metrics/visits.md) metric over time with the Adobe-provided 'Return visits' segment applied.
* Visit number: Uses the [Visit number](/help/components/dimensions/visit-number.md) dimension.
* Sales cycle: Folder for purchase-related reports.
  * Customer loyalty: Uses the [Customer loyalty](/help/components/dimensions/customer-loyalty.md) dimension.
  * Days before first purchase: Uses the [Days before first purchase](/help/components/dimensions/days-before-first-purchase.md) dimension.
  * Days since last purchase: Uses the [Days since last purchase](/help/components/dimensions/days-since-last-purchase.md) dimension.
  * Daily unique customers: Trends [Daily unique visitors](/help/components/metrics/unique-visitors.md) over time with the Adobe-provided 'purchasers' segment applied.
  * Weekly unique customers: Trends [Weekly unique visitors](/help/components/metrics/unique-visitors.md) over time with the Adobe-provided 'purchasers' segment applied.
  * Monthly unique customers: Trends [Monthly unique visitors](/help/components/metrics/unique-visitors.md) over time with the Adobe-provided 'purchasers' segment applied.
  * Quarterly unique customers: Trends [Quarterly unique visitors](/help/components/metrics/unique-visitors.md) over time with the Adobe-provided 'purchasers' segment applied. Quarters are January-March, April-June, July-September, and October-December.
  * Yearly unique customers: Trends [Yearly unique visitors](/help/components/metrics/unique-visitors.md) over time with the Adobe-provided 'purchasers' segment applied.

## Visitor profile

Contains reports about who visits your site.

* Geosegmentation: Reports about where on the globe hits to your site came from.
  * Countries: Uses the [Countries](/help/components/dimensions/countries.md) dimension.
  * Region: Uses the [Regions](/help/components/dimensions/regions.md) dimension.
  * Cities: Uses the [Cities](/help/components/dimensions/cities.md) dimension.
  * US states: Uses the [US states](/help/components/dimensions/us-states.md) dimension.
  * US DMA: Uses the [US DMA](/help/components/dimensions/us-dma.md) dimension.
* Languages: Uses the [Language](/help/components/dimensions/language.md) dimension.
* Time zones: Uses the time zone dimension (retired in Analysis Workspace). Dimension items are the GMT offset of the hit.
* Domain: Uses the [Domain](/help/components/dimensions/domain.md) dimension.
* Top level domain: Uses the top level domain dimension (retired in Analysis Workspace). It groups the [domains](/help/components/dimensions/domain.md) dimension into higher-level categories, typically by country of the domain.
* Technology: Folder containing reports around what the visitor used to access your site.
  * Browsers: Uses the [Browsers](/help/components/dimensions/browser.md) dimension.
  * Browser type: Uses the [Browser type](/help/components/dimensions/browser-type.md) dimension.
  * Browser width: Uses the [Browser width - bucketed](/help/components/dimensions/browser-width.md) dimension.
  * Browser height: Uses the [Browser height - bucketed](/help/components/dimensions/browser-height.md) dimension.
  * Operating system: Uses the [Operating systems](/help/components/dimensions/operating-systems.md) dimension.
  * Operating system type: Uses the [Operating system types](/help/components/dimensions/operating-system-types.md) dimension.
  * Monitor color depth: Uses the [Color depth](/help/components/dimensions/color-depth.md) dimension.
  * Monitor resolution: Uses the [Monitor resolution](/help/components/dimensions/monitor-resolution.md) dimension.
  * Java: Uses the [Java enabled](/help/components/dimensions/java-enabled.md) dimension.
  * JavaScript: Uses the JavaScript enabled dimension (retired in Analysis Workspace). Dimension items are 'Enabled', 'Disabled', or 'Unknown', depending on if the browser has JavaScript enabled.
  * JavaScript version: uses the JavaScript version dimension (retired in Analysis Workspace). Dimension items show the version of JavaScript that the browser uses.
  * Cookies: Uses the [Cookie support](/help/components/dimensions/cookie-support.md) dimension.
  * Connection types: Uses the [Connection type](/help/components/dimensions/connection-type.md) dimension.
  * Mobile carrier: Uses the [Mobile carrier](/help/components/dimensions/mobile-dimensions.md) dimension.
* Visitor state: Uses the State dimension (retired in Analysis Workspace). Dimension items originate from the [`state`](../../implement/vars/page-vars/state.md) variable.
* Visitor ZIP/postal code: Uses the [Zip code](/help/components/dimensions/zip-code.md) dimension.

## Custom conversion

Contains reports specific to your implementation. Custom conversion reports use [eVars](/help/components/dimensions/evar.md) as the dimension.

## Custom traffic

Contains reports specific to your implementation. Custom traffic reports use [props](/help/components/dimensions/prop.md) as the dimension.

## Marketing channels

Contains reports involving [Marketing channels](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Channel overview report: A custom report specific to Reports & Analytics. Uses marketing channels as dimension items, with metrics using first or last touch attribution.
* First touch channel: Uses the [First touch channel](/help/components/dimensions/first-touch-channel.md) dimension.
* First touch channel detail: Uses the [First touch channel detail](/help/components/dimensions/first-touch-detail.md) dimension.
* Last touch channel: Uses the [Last touch channel](/help/components/dimensions/last-touch-channel.md) dimension.
* Last touch channel detail: Uses the [Last touch channel detail](/help/components/dimensions/last-touch-detail.md) dimension.

## Bookmarks

Contains reports that you bookmarked. See [Bookmarks](bookmarks.md) for more information.

## Dashboards

Contains dashboards that you created. See [Dashboards](dashboard.md) for more information.

## Targets

Contains targets that you created. See [Targets](targets.md) for more information.

>[!NOTE]
>
>If you can't find your report on this help page, it is possible that your administrator renamed or adjusted folders. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.
