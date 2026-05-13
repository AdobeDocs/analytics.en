---
description: Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.
title: Internal URL Filters
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
TQID: https://experienceleague.adobe.com/J78ImTXRPFm6aMHqrxJXZOUVyG-ETnutipYYo2wrofc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Internal URL filters

Internal URL filters allow you to identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**

A referrer, or referring page, is typically the page from which a visitor entered your site. To avoid skewing data, you can filter out internal referrers. Dimensions that rely on internal URL filters include [Referrer](/help/components/dimensions/referrer.md), [Referring domain](/help/components/dimensions/referring-domain.md), [Marketing channels](/help/components/dimensions/marketing-channel.md), and other traffic source dimensions.

[Marketing channel processing rules](../marketing-channels/mc-proc-rules.md) provide "[!UICONTROL Matches internal URL filters]" as possible rule criteria.

>[!IMPORTANT]
>
>Some report suites have an internal URL filter of a period (`.`) configured by default. When this filter exists, all traffic is classified as internal. Referrer reports do not work until this filter is removed and replaced with one or more desired internal domains.

* View all existing filters under the **[!UICONTROL Current Filters]** section.
* Add a filter using the text box under the **[!UICONTROL Add Filter]** section, then click **[!UICONTROL Add]**.

Filters operate using **contains** logic against the full URL. Adobe recommends omitting protocol (`https://`) and subdomains when creating filters, unless traffic from separate subdomains is desired as external traffic.
