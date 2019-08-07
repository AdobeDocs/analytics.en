---
description: The data connectors integration for appFigures uses Analytics variables to track various appFigures metrics.
seo-description: The data connectors integration for appFigures uses Analytics variables to track various appFigures metrics.
seo-title: Analytics Integration Variables
title: Analytics Integration Variables
uuid: 08d5b714-1c97-4be6-aae8-1f8192535425
index: y
internal: n
snippet: y
---

# Analytics Integration Variables{#analytics-integration-variables}

The data connectors integration for appFigures uses Analytics variables to track various appFigures metrics.

The following table describes the Analytics variables automatically activated for the appFigures integration.

## Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

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

