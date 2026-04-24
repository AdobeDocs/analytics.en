---
description: You can enable media in Analytics to reserve a special set of Media Solution Variables for use in measurement and reporting.
title: Media management
feature: Admin Tools
uuid: a841a5a8-6d47-478d-b02b-6c1647fb04ce
exl-id: b6dc8d93-3f89-4671-a4c3-18614667bf4e
TQID: https://experienceleague.adobe.com/O-5lvUKHMEU-k-HCAKNJzwv1Rv4G-KrCQBsCGi5ieUE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Media management

You can use this interface to reserve variables for use in media measurement and reporting. When These variables behave similarly to eVars, props, and events, but do not count against any variable limits. After they are enabled, your users will see a new set of Media reports in the Analytics menus.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Media Management]**.

The following Media Management options are available when editing a report suite:

* [!UICONTROL **Media Reporting**]

  Use these check boxes to enable dimensions and metrics specific to streaming media services.

  * [Media core dimensions](/help/components/dimensions/sm-core.md)
  * [Media core metrics](/help/components/metrics/sm-core.md)
  * [Media ad dimensions](/help/components/dimensions/sm-ads.md)
  * [Media ad metrics](/help/components/metrics/sm-ads.md)
  * [Media chapter dimensions](/help/components/dimensions/sm-chapters.md)
  * [Media chapter metrics](/help/components/metrics/sm-chapters.md)
  * [Media quality dimensions](/help/components/dimensions/sm-quality.md)
  * [Media quality metrics](/help/components/metrics/sm-quality.md)
  * [Video metadata dimensions](/help/components/dimensions/sm-video-metadata.md)
  * [Video metadata metrics](/help/components/metrics/sm-video-metadata.md)
  * [Audio metadata dimensions](/help/components/dimensions/sm-audio-metadata.md)
  * [Player state tracking metrics](/help/components/metrics/sm-player-state.md)

* [!UICONTROL **Media Classifications**]

  Classifications specific to streaming media services dimensions are available on the [!UICONTROL Media Classifications] page. They operate similarly to [Conversion classifications](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md) available for conversion variables. Enabling certain components under [!UICONTROL Media Reporting] automatically create classification dimensions for you. You can use this interface to create your own classification dimensions or upload classification data.

For general information about incorporating streaming media data in Adobe Analytics, see the [Adobe streaming media services overview](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-overview).
