---
title: Convert Your Legacy Report Builder Workbooks
description: Understand how to convert your legacy requests to datablocks in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
---
# Convert legacy Report Builder workbooks to datablocks

As part of the move to a new Report Builder functionality, you can quickly convert your current legacy Report Builder based workbooks to use the new Report Builder functionality. 

>[!IMPORTANT]
>
>Duplicate each workbook and rename one version before you convert the workbook. That ensures that you always have a copy of the original workbook, should you need it.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convert workbooks](https://video.tv.adobe.com/v/3434957?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



1. Set up the new Report Builder by [following these instructions](/help/analyze/report-builder/report-builder-setup.md).

1. Open Excel and select ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** from the Excel ribbon bar. 

1. Click **[!UICONTROL Login]** and log in to Report Builder.

1. The Report Builder add-in detects if this workbook contains [legacy Report Builder](/help/analyze/legacy-report-builder/home.md) requests.

    ![upgrade workbook prompt](assets/upgrade-workbook.png){zoomable="yes"}

1. If one or more legacy requests are found, click **[!UICONTROL Upgrade]** in the **[!UICONTROL Upgrade workbook]** dialog to upgrade the workbook. 

    >[!NOTE]
    >
    >You have to upgrade each request individually. Bulk upgrade is not supported.


1. A **[!UICONTROL Warning]** dialog appears that alerts you to changes to the workbook if you upgrade. It also urges you to create a backup of your legacy workbook before proceeding.

    ![upgrade warning](assets/upgrade-warning.png){zoomable="yes"}

1. Click **[!UICONTROL Proceed]** to continue with the upgrade.

    If the upgrade is successful, a **[!UICONTROL The workbook upgrade is now completed]** notification appears.

    ![upgrade complete](assets/upgrade-complete.png)

    * Select **[!UICONTROL Close]** to close the notification and continue to work in the workbook with updated requests for the new Report Builder. 

    * Select **[!UICONTROL Download upgrade report]** to download and open a new Excel workbook that shows the result of the upgrade. For an example, see below.

      ![Excel Report Builder upgrade report workbook](assets/upgrade-report.png)

You can now [manage the data block](/help/analyze/report-builder/manage-reportbuilder.md).


## Legacy Report Builder features not supported {#unsupported}

Some legacy Report Builder functionality is no longer available in the new Report Builder

* Real-time requests

* Path/Fallout reporting

* FTP option for scheduled reports

* Visitors metrics. The following metrics will all be converted to "unique visitors", even though the reporting result may not be an exact match: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly`, and `visitorsyearly`. This also applies to `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly`, and `mobilevisitorsyearly`.

## Schedule a converted workbook {#schedule}

See [Schedule a converted workbook](/help/analyze/report-builder/schedule-reportbuilder.md) in the scheduling article.
