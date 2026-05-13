---
title: Tracking opt-out reason
description: Previews what data would be excluded if you enabled Privacy Settings.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Tracking opt-out reason

*This page refers to the [dimension](overview.md) that lets you see potential data impact from enabling certain Report Suite settings. It is not related to the [Adobe Experience Cloud ID Opt-in Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html).*

The 'Tracking opt-out reason' dimension acts as a preview to data that would be excluded if you enabled Privacy Settings. This dimension is primarily used to determine if your implementation would be negatively impacted if you enabled [Privacy Settings](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) under Report Suite Settings.

Typical implementations see 1% or less of their overall report suite traffic under this dimension if Privacy Settings have not yet been enabled. Percentages higher than 1% of all traffic suggests a potential implementation problem that prevents AppMeasurement from setting first-party cookies.

## Populate this dimension with data

This dimension works out of the box for all implementations that have not yet enabled [Privacy Settings](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). If your organization has already enabled the **[!UICONTROL Remove users who have blocked all cookies]** setting for both desktop and mobile browsers, this dimension does not contain data.

## Dimension items

Dimension items include `"Cookies disabled by Desktop Browser"` and `"Cookies disabled by Mobile Browser"`.

* **Cookies disabled by Desktop Browser**: The visitor blocked cookies using a desktop browser, and **[!UICONTROL Remove users who have blocked all cookies on desktop browsers]** is disabled.
* **Cookies disabled by Mobile Browser**: The visitor blocked cookies using a mobile browser, and **[!UICONTROL Remove users who have blocked all cookies on mobile browsers]** is disabled.
