---
description: Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.
title: Internal URL Filters
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
---

# Internal URL Filters

Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**

A referrer, or referring page, is typically the page from which a visitor entered your site. To avoid skewing data, you can filter out internal referrers. Reports exclude filtered referrers from the [Referrers](/help/components/dimensions/referrer.md) dimension, the [Referring domains](/help/components/dimensions/referring-domain.md) dimension, and other traffic source dimensions.

The most common reason traffic sources reports don't populate data is that the Internal URL Filter List isn't defined. To check which Internal URL Filters have been set up on a report suite, follow these steps. To avoid this, remove the rule listing a period (.) as a filter, and add your own site.

The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.
