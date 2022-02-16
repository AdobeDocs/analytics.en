---
description: Create a basic container for data collection in Adobe Analytics
title: Create a report suite
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
---
# Create a report suite

A report suite is a silo of data that Adobe Analytics uses to pull reports. An organization can have many report suites, each containing different data sets. While separate report suites were important in the past, having a single report suite has become more advantageous. The introduction of [virtual report suites](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) and report time processing allows admins to create your own subsets of data, allowing the flexibility to obtain both global and site-specific data.

This article is designed for system-level administrators or Adobe Analytics admins to prepare for data collection.

## Prerequisites

[Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md): Ensure that a system-level administrator has granted you access to Adobe Analytics via the Experience Cloud Admin Console.

## Create a report suite {#create-report-suite}

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Click **[!UICONTROL Create New]** > **[!UICONTROL Report Suite]**.
1. To copy a report suite's settings, in the template list, select either a predefined template or an existing report suite to use as a [template.](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)

   >[!NOTE]
   >
   >Only settings can be copied, not the data. If Customer Care is copying the settings over, you will need to provide a written confirmation to the disclaimer provided by Customer care about the risks involved. See [Settings not copied from a source report suite](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) for more information.

1. Fill in the fields described in [New Report Suite.](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Click **[!UICONTROL Create Report Suite]**.

A report suite ID has a maximum length of 40 bytes. A report suite friendly name has a maximum length of 255 bytes.

## Troubleshooting

**After logging in to the Experience Cloud, the Analytics icon is greyed out.**

This means that your account has not been granted the correct permissions to Analytics. Work with a system-level admin in your organization to ensure you belong to a profile with adequate permissions to access Adobe Analytics.

**After logging in to Adobe Analytics, the 'Welcome to Adobe Analytics' popup and dropdown is missing.**

Ensure that you've logged in through the [Experience Cloud](https://experience.adobe.com), and not through my.omniture.com. User who log in through my.omniture.com do not have the report suite setup wizard available.

## Next steps

[Create an Adobe Analytics tag property ](/help/implement/launch/create-analytics-property.md): Create an area to manage your Analytics implementation
