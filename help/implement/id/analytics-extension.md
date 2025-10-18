---
title: Visitor identification using the Adobe Analytics tag extension
description: Correctly identify visitors when implementing the Adobe Analytics tag extension.
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
   * If you do not participate in the Managed certificate program, tracking server is typically a subdomain of `omtrdc.net` or `2o7.net`, making the `s_vi` cookie a third-party cookie. Due to modern browser privacy practices, third-party cookies are rejected by most browsers. Once rejected, AppMeasurement attempts to set a first-party fallback cookie (`fid`) instead.

If you correctly set [!UICONTROL SSL Tracking Server], then no further visitor identification measures are required.

## Identifying visitors using `visitorID` (Not recommended)

>[!IMPORTANT]
>
>Adobe advises against using this method to identify visitors.

Using the **[!UICONTROL Visitor ID]** variable allows your organization complete independent control identifying visitors. If you set [!UICONTROL Visitor ID] using a data element, note the following limitations:

* Every hit must contain the same [!UICONTROL Visitor ID] value to be counted as a single visitor.
  * Any hits that omit the [!UICONTROL Visitor ID] data element automatically attempt to use another visitor identification method, treating them as a separate visitor.
  * Any hits that contain a different [!UICONTROL Visitor ID] value from a previous hit are treated as a separate visitor.
  * Adobe does not offer any way to stitch hits using different visitor IDs together.
* Shared audiences, Analytics for Target, and Customer attributes are not supported with visitors identified using [!UICONTROL Visitor ID].

See [`visitorID`](/help/implement/vars/config-vars/visitorid.md) for implementation instructions using this variable.
