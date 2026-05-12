---
title: Java enabled
description: Determines if Java is enabled in the browser.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Java enabled

The 'Java enabled' [dimension](overview.md) determines if the browser at the time has Java enabled. It is helpful in cases where you want to introduce Java-based functionality on your site and want to know how many visitors already have Java enabled. For those who have Java disabled, you can provide an alternative or instructions on how to enable it.

## Populate this dimension with data

This dimension retrieves data from the [`v` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data by detecting if Java is enabled in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `v` query string parameter containing "Y" or "N" if you would like to use this dimension.

## Dimension items

Dimension items include "Enabled", "Disabled", and "Unknown".

* **Enabled**: Java is enabled in the browser. The `v` query string contained the value "Y".
* **Disabled**: Java is disabled in the browser, or otherwise does not support Java. The `v` query string contained the value "N".
* **Unknown**: AppMeasurement was unable to determine Java support. The `v` query string was not present in the image request.
