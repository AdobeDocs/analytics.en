---
title: eVar for Dimensions
description: A custom dimension you can use in reporting.
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
---
# eVar

*This help page describes how eVars work as a dimension. For information on how to implement eVars, see [eVars](/help/implement/vars/page-vars/evar.md) in the Implement user guide.*

eVars are custom variables that you can use however you'd like. If you have a [solution design document](/help/implement/prepare/solution-design.md), most dimensions specific to your organization end up as [!UICONTROL eVars]. By default, eVars persist beyond the hit they are set on. You can customize their expiration and allocation under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in [!UICONTROL Report suite settings].

The number of available eVars depends on your contract with Adobe. Up to 250 eVars are available if your contract with Adobe supports it.

The (upper or lower) case used in reporting is based on the first value the backend system registers. This value could either be the first instance ever seen or vary by some time period (e.g., monthly), depending on the variety and quantity of data associated with the report suite.

## Populate eVars with data

Each eVar collects data from the [`v1` - `v250` query string](/help/implement/validate/query-parameters.md) in image requests. For example, the `v1` query string parameter collects data for eVar1, while the `v222` query string parameter collects data for eVar222.

AppMeasurement, which compiles JavaScript variables into an image request for data collection, uses the variables `eVar1` - `eVar250`. See [eVar](/help/implement/vars/page-vars/evar.md) in the Implement user guide for implementation guidelines.

## Dimension items

Since eVars contain custom strings in your implementation, your organization determines what the dimension items are for each eVar. Make sure you record the purpose of each eVar and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).

## How eVars work

When you send data to Adobe Analytics, data collection servers translate the hit into a single row of data with hundreds of columns. Two columns are dedicated to each eVar; one for direct data collection, and the other for persisting values.

* A standard column contains data sent to Adobe from the image request.
* A "post" column contains persistent data, which depends on the eVar's expiration and allocation.

Under almost all circumstances, the `post_evar` column is used in reports.

### How eVars tie to metrics

Success events and eVars are frequently defined in different image requests. The `post_evar` column allows eVar values to tie themselves to events, showing data in reporting. Take the following visit for example:

1. A visitor arrives to your site on your home page.
2. They search for "cats" using your site's internal search. Your implementation uses eVar1 for internal search.
3. They view a product, and proceed through the checkout process.

A simplified version of the raw data would look similar to the following:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` | | | |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` | | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` | | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` | | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` | | `cats` | `purchase` |

* The `visitor_id` column ties hits to the same visitor. In actual raw data, the concatenated values of `visid_high` and `visid_low` determine visitor ID.
* The `pagename` column populates the Pages dimension.
* The `evar` column determines the hits when eVar1 was explicitly set.
* The `post_evar1` carries the previous value, dependent on the variable's allocation and expiration set under report suite settings.
* The `event_list` column contains all metric data. For this example, `event1` is 'Searches', and the other events are standard shopping cart metrics. In actual raw data, `event_list` contains a comma-delimited set of numbers with a lookup table tying those numbers to a metric.

### Translating data collection to reporting

Tools in Adobe Analytics, such as Analysis Workspace, work off of this collected data. For example, if you pulled a report using eVar1 as the dimension and Orders as the metric, you would see a report similar to the following:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace pulls this report using the following logic:

* Look through all `event_list` values, and pick out all the hits with `purchase` in them.
* Out of those hits, display the `post_evar1` value.

### The importance of allocation and expiration

Since allocation and expiration determine what values persist, they are vital in getting the most value out of an analytics implementation. Adobe highly recommends that you discuss within your organization how multiple values for each eVar are handled (allocation) and when eVars stop persisting data (expiration).

* By default, an eVar uses last allocation. New values overwrite persisted values.
* By default, an eVar uses an expiration of visit. Once a visit ends, values stop copying over from row to row in the `post_evar` column.

You can change eVar allocation and expiration under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in Report suite settings.

## Value of eVars over props

Adobe recommends using eVars in most cases, supported through the following:

* eVars have a 255-byte limit in reports. Props have a 100-byte limit.
* Props by default do not persist beyond the hit they are set. eVars have custom expiration, allowing you to determine when an eVar no longer gets credit for a subsequent event. However, if you use [report time processing](/help/components/vrs/vrs-report-time-processing.md), both props and eVars can use a custom attribution model.
* Adobe supports up to 250 eVars, and only 75 props.

See [prop](prop.md) for more comparisons between props and eVars.
