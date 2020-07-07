---
description: Before activating this integration, review the following items against your deployments of Adobe Analytics® and your email software.
title: Before You Activate This Integration
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
---

# Before You Activate This Integration {#before-you-activate-this-integration}

Before activating this integration, review the following items against your deployments of Adobe Analytics® and your email software.

Doing so will ensure that the appropriate best practices or pre-requisites are in place prior to activation, which will result in an optimal and successful integration.

## Adobe Analytics Requirements{#adobe-analytics-requirements}

Review the following information about this data connectors integration as it relates to Adobe Analytics:

* **Report-Suite Specific:** Be advised that this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration and that the report suite contains data.
* **Available and configured Analytics variables:** This integration requires 10 custom events and 1 custom eVar. See [Analytics Integration Variables](appfigures-before-activation.md#analytics-integration-variables).

* **Report Suite initialized with Live data:** If you are creating a brand new report suite for this integration it needs to have received some (at least one hit) data via live tracking appFigures requirements. If live data has not been recorded, the report suite will not be ready to receive integrated App Store data.

* **Existing integration with App store:** This integration back fills data for 13 months. In order to avoid any overlap with any previous App store data provider you might have had, please reach out to your appFigures representative. Let them know the last date you received data. appFigures will adjust the back fill period accordingly.

## appFigures Requirements{#appfigures-requirements}

Review the following information about this data connectors integration as it relates to appFigures:

* **Current Customer of appFigures:** This integration requires you to be a user of both Adobe and appFigures. If you are not currently a user of the appFigures Enterprise Plan, you will not have the information necessary to complete the integration wizard. Please visit appFigures on the web for more information.
* **appFigures Account Key:** An appFigures Account Key is required to activate the appFigures Data Connector. This account key can be generated in the "Add-ons" section. Refer to [Configure the Integration](../appfigures-overview/t-appfigures-integration.md) for more information.

* **Data Finalization**: Download, sales, and ranking information is synchronized each day for the previous 7 days. After 7 days data is considered final and is no longer updated.

## Pricing{#pricing}

This data connectors integration includes pricing considerations that you need to be aware of.

The following sections contain more information:

### Adobe Pricing Considerations {#section-2d1c79c895a5479bad8fdd97961ba6a3}

There are currently no fees to active this integration. However, you might see a slight server call increase due to the data sources import.

### appFigures Pricing Considerations {#section-c6afad08c34b43e3a7a3637eea3328c3}

There are currently no fees associated with this integration. This integration is currently only available to Enterprise customers. Please [contact appFigures](https://appfigures.com/support/contact) for more information.

## Analytics Integration Variables{#analytics-integration-variables}

The data connectors integration for appFigures uses Analytics variables to track various appFigures metrics.

The following table describes the Analytics variables automatically activated for the appFigures integration.

### Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>This integration uses dedicated variables for app store data, so you do not need to assign custom commerce variables and events.

|  Variable Type  | Name  | Population Method  | Description  |
|---|---|---|---|
|  eVar  | App Store Object ID  | Imported from appFigures.  | Configure this eVar with Visit expiration, Most recent allocation, and basic subrelations.  |
|  event (numeric)  | App Store Downloads  | Imported from appFigures.  | The number of mobile application downloads.  |
|  event (numeric)  | App Store Purchases (in app)  | Imported from appFigures.  | The number of in-app purchases and subscriptions.  |
|  event (numeric)  | App Store Rank  | Imported from appFigures.  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  event (numeric)  | App Store Rank Divisor  | Imported from appFigures.  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  event (numeric)  | App Store Rating  | Imported from appFigures.  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  event (numeric)  | App Store Rating Divisor  | Imported from appFigures.  | Used to define the Average appFigures Calculated Metric. Not used directly.  |
|  event (currency)  | App Store Revenue (in app)  | Imported from appFigures.  | The amount of in-app revenue minus the store fee.  |
|  event (currency)  | App Store Revenue (one off)  | Imported from appFigures.  | Total revenue from app purchases minus the store fee.  |
|  event (currency)  | App Store Royalties (in app)  | Imported from appFigures.  | Not used  |
|  event (currency)  | App Store Royalties (one off)  | Imported from appFigures.  | Not used  |
