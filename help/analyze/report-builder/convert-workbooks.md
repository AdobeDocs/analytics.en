---
title: How to convert your legacy Report Builder workbooks to datablocks
description: Describes how convert your legacy requests to datablocks
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
---
# Convert legacy Report Builder workbooks to datablocks

As part of the move to a new Report Builder technology, you can quickly convert your current legacy workbooks to Javascript-based workbooks. 

>[!IMPORTANT]
>
>Duplicate each workbook and rename one version before you convert it. That way, you still have a copy of the original workbook, should you need it.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convert workbooks](https://video.tv.adobe.com/v/3434957?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



1. Set up the new Report Builder by [following these instructions](/help/analyze/report-builder/report-builder-setup.md).

1. Open Excel and click the Adobe Report Builder icon at the top right. 

1. Click **[!UICONTROL Login]** and log in to Report Builder.

1. The Report Builder add-in detects if this workbook contains [Legacy Report Builder](/help/analyze/legacy-report-builder/home.md) requests.

    ![upgrade workbook prompt](assets/upgrade_workbook.png)

1. If one or more legacy requests are found, click **[!UICONTROL Upgrade]** to upgrade a workbook. 

    >[!NOTE]
    >
    >You have to upgrade each request individually. Bulk upgrade is not supported.


1. A warning appears that alerts you to changes to the workbook if you upgrade. It also urges you to create a backup of your legacy workbook before proceeding.

    ![upgrade warning](assets/upgrade_warning.png)

1. Click **[!UICONTROL Proceed]** to continue with the upgrade.

    If the upgrade is successful, the following completion notice appears:

    ![upgrade complete](assets/upgrade_complete.png)

1. (Optional) Click **[!UICONTROL Download upgrade report]**. This report contains the status on each data block that was upgraded. 

You can now [manage the data block](/help/analyze/report-builder/manage-reportbuilder.md).


## Legacy Report Builder features not supported in the New Report Builder {#unsupported}

When comparing the functionality of Legacy Report Builder to the new Report Builder Add-in, some legacy functionality is no longer available:

- Real-time requests

- Path/Fallout reporting

- FTP option for scheduled reports

- Visitors metrics. The following metrics will all be converted to "unique visitors", even though the reporting result may not be an exact match: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly`, and `visitorsyearly`. This also applies to `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly`, and `mobilevisitorsyearly`.

## Schedule a converted workbook {#schedule}

See [Schedule a converted workbook](/help/analyze/report-builder/schedule-reportbuilder.md) in the scheduling article.