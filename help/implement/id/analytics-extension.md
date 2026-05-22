---
title: Visitor identification using the Adobe Analytics tag extension
description: Correctly identify visitors when implementing the Adobe Analytics tag extension.
exl-id: de534c69-0f43-45eb-86da-20d3cd3f363d
TQID: 'https://experienceleague.adobe.com/i38Vo-39aUwJOp3HoS-bb2jqwSSV0oqeR0lkjOJqcgs'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Visitor identification using the Adobe Analytics tag extension

The Adobe Analytics tag extension provides allows you to implement AppMeasurement using a tag management interface. Since this tag extension is essentially AppMeasurement under the hood, it offers similar methods to identify visitors and requires a separate tag extension for the Visitor ID Service.

## Identifying visitors using the Visitor ID Service (recommended)

To use the Visitor ID Service using the Adobe Analytics tag extension, include the Experience Cloud ID Service tag extension in your tag property.

1. Log in to [experience.adobe.com](https://experience.adobe.com) using your Adobe ID credentials.
1. Navigate to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.
1. Locate the desired tag property.
1. Navigate to **[!UICONTROL Extensions]**, then select the **[!UICONTROL Catalog]** tab.
1. Locate the **[!UICONTROL Experience Cloud ID Service]** extension, then select **[!UICONTROL Install]**.

The tag extension automatically obtains your IMS org ID, so no additional configuration is necessary.

## Identifying visitors using the `s_vi` cookie (Not recommended)

>[!IMPORTANT]
>
>Adobe advises against using this method to identify visitors.

If your organization does not use the Visitor ID Service tag extension, the Adobe Analytics tag extension uses its own form of visitor identification. When a visitor arrives to your site for the first time, the extension checks for a [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie. This cookie is set at the domain matching **[!UICONTROL SSL Tracking Server]** (for HTTPS) or **[!UICONTROL Tracking Server]** (for HTTP) when [configuring the tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview).

* If you participate in the [Managed certificate program](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), your tracking server would typically be a first-party domain, making `s_vi` cookies first-party.
* If you do not participate in the Managed certificate program, tracking server is typically a subdomain of `adobedc.net`, `omtrdc.net`, or `2o7.net`, making the `s_vi` cookie a third-party cookie. Due to modern browser privacy standards, third-party cookies are rejected by most browsers. Once rejected, AppMeasurement attempts to set a first-party fallback cookie (`fid`) instead.

If you correctly set [!UICONTROL SSL Tracking Server], then no further visitor identification measures are required.

## Identifying visitors using `visitorID` (Not recommended)

>[!IMPORTANT]
>
>Adobe advises against using this method to identify visitors.

Using the **[!UICONTROL Visitor ID]** variable allows your organization complete independent control identifying visitors. If you set [!UICONTROL Visitor ID] using a data element, note the following limitations:

* Every hit must contain the same [!UICONTROL Visitor ID] value to be counted as a single visitor.
  * Any hits that omit the [!UICONTROL Visitor ID] data element automatically attempt to use another visitor identification method, treating them as a separate visitor.
  * Any hits that contain a different [!UICONTROL Visitor ID] value from a previous hit are treated as a separate visitor.
  * Adobe does not offer a way to stitch hits using different visitor IDs together in Adobe Analytics.
* Shared audiences, Analytics for Target, and Customer attributes are not supported with visitors identified using [!UICONTROL Visitor ID].

See [`visitorID`](/help/implement/vars/config-vars/visitorid.md) for implementation instructions using this variable.
