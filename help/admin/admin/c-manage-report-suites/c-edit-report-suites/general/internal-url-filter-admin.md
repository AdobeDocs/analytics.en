---
description: Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.
title: Internal URL Filters
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
---

# Internal URL filters

Internal URL filters identify the referrers that you consider internal to your site. They help traffic sources reports populate data and help filter internal traffic.

## Add an internal URL filter

A referrer, or referring page, is typically the page from which a visitor entered your site. To avoid skewing data, you can filter out internal referrers. Reports exclude filtered referrers from the [Referrers](/help/components/dimensions/referrer.md) dimension, the [Referring domains](/help/components/dimensions/referring-domain.md) dimension, and other traffic source dimensions.

To add an internal URL filter to a report suite:

1. Select **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** to access the Report Suite Manager.

1. Select the report suite where you want to add an internal URL filter, then select **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**.

1. In the Add Filter section, in the provided field, begin typing the URL of the page that you want to filter, then select [!UICONTROL **Add**].

   The URL that you added is now visible in the [!UICONTROL **Current Filters**] section.

## View existing internal URL filters

The most common reason traffic sources reports don't populate data is that the internal URL filter list isn't defined. 

To check which internal URL filters are configured for a report suite: <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")

1. Select **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** to access the Report Suite Manager.

1. Select the report suite where you want to check which internal URL filters are configured, then select **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**.

   All existing filters are listed in the [!UICONTROL **Current Filters**] section.
