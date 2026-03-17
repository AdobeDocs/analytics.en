---
title: Convert Legacy Report Builder Workbooks
description: Learn how to migrate and convert legacy Report Builder workbooks to the new Report Builder. Follow step-by-step instructions in this migration guide on how to seamless convert your Adobe Analytics based workbooks.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
---
# Convert legacy Report Builder workbooks

The legacy Report Builder is end-of-life in June 2026. You should migrate your workbooks from the legacy Report Builder to the new Report Builder. The new Report Builder provides a convenient way to migrate workbooks quickly that are created with the legacy Report Builder.

>[!IMPORTANT]
>
>Duplicate each workbook and rename one version before you convert the legacy workbook. That ensures that you always have a copy of the original legacy workbook, should you need it.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convert workbooks](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!NOTE]
>
>To convert legacy workbooks, you must have first [set up the new Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Open a legacy workbook

To open a legacy workbook, you can:
  
* Open a scheduled legacy workbook from the **[!UICONTROL Schedule]** tab in the [Report Builder hub](report-builder-hub.md). This action is the preferred method for scheduled legacy workbooks. You get the option to use the schedule that is associated with the legacy workbook as soon as you [schedule the converted legacy workbook](#schedule-a-converted-legacy-workbook).

  1. Open [!DNL Excel] and select ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** from the [!DNL Excel] ribbon bar. 

  1. Select **[!UICONTROL Login]** and log in to Report Builder.

  1. Select **[!UICONTROL Schedule]** in the [Report Builder hub](report-builder-hub.md).
  1. Select the **[!UICONTROL Legacy]** tab. The tab lists the legacy Report Builder based scheduled workbooks that you have created.

     ![Legacy workblooks](assets/upgrade-legacy-schedule.png)

  1. Select ![SelectBox](/help/assets/icons/SelectBox.svg) the scheduled workbook that you want to convert from the list, and select ![Download](/help/assets/icons/Download.svg). The workbook is downloaded and opens in a new window in [!DNL Excel]. You can now [convert the legacy Report Builder workbook](#convert-a--workbook).


* Open a legacy workbook directly from your local computer or network. When you use this method, you are not offered to use the schedule that might be associated with the legacy workbook. <br/>When the legacy workbook is open in [!DNL Excel]:

  1. Select ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** from the [!DNL Excel] ribbon bar.
  1. Select **[!UICONTROL Login]** and log in to Report Builder.
  1. Then [convert the legacy workbook](#convert-a-workbook).


## Convert a legacy workbook

To convert your legacy workbook:

1. Once you open a legacy workbook, the new Report Builder detects if this workbook contains [legacy Report Builder](/help/analyze/legacy-report-builder/home.md) requests.

    ![Screenshot of the [!DNL Excel] Report Builder upgrade report showing migration upgrade](assets/upgrade-workbook.png){zoomable="yes"}

1. If one or more legacy requests are found, click **[!UICONTROL Upgrade]** in the **[!UICONTROL Upgrade workbook]** dialog to upgrade the workbook. 

    >[!NOTE]
    >
    >You have to upgrade each request individually. Bulk upgrade is not supported.


1. A **[!UICONTROL Warning]** dialog appears that alerts you to changes to the workbook if you upgrade. It also urges you to create a backup of your legacy workbook before proceeding.

    ![Screenshot of the [!DNL Excel] Report Builder upgrade report showing migration warning](assets/upgrade-warning.png){zoomable="yes"}

1. Click **[!UICONTROL Proceed]** to continue with the upgrade.

    If the upgrade is successful, a **[!UICONTROL The workbook upgrade is now completed]** notification appears.

    ![Screenshot of the [!DNL Excel] Report Builder upgrade report showing migration completed](assets/upgrade-complete.png)

    * Select **[!UICONTROL Close]** to close the notification and continue to work in the workbook with updated requests for the new Report Builder. 

    * Select **[!UICONTROL Download upgrade report]** to download and open a new [!DNL Excel] workbook that shows the result of the upgrade. For an example, see below.

      ![Screenshot of the [!DNL Excel] Report Builder upgrade report showing migration report](assets/upgrade-report.png)

You can now [manage the data blocks](/help/analyze/report-builder/manage-reportbuilder.md) in the workbook. These data blocks are the result of the upgrade and replace your legacy Report Builder requests.


## Schedule a converted legacy workbook

 You have the option to use the schedule details from the legacy workbook that you have downloaded and opened from the **[!UICONTROL Schedule]** tab in the Report Builder hub. This option is not available for legacy workbooks with schedule details that you open from your local computer or network.

1. To schedule a converted legacy workbook with a legacy schedule:

   * Select **[!UICONTROL Send workbook]** from the Report Builder hub, or 
   * Select **[!UICONTROL Schedule workbook]** from the **[!UICONTROL Workbooks]** tab available in the **[!UICONTROL Schedules]** tab in Report Builder.

1. You are offered to use the schedule details from the legacy workbook as the default schedule settings.

   ![Screenshot of the [!DNL Excel] Report Builder legacy schedule settings options](assets/upgrade-legacy-schedule-convert.png)

   * Select **[!UICONTROL Use]** to use the legacy schedule details. The schedule details are prepopulated in the [Send workbook](schedule-reportbuilder.md#schedule-a-workbook) interface.
   * Select **[!UICONTROL Don't use]** to not use the legacy schedule details.
   * Select **[!UICONTROL Cancel]** to cancel.

   Select **[!UICONTROL Remove legacy metadata from future use]** to not use the legacy schedule details for this workbook in the future.


## Migrate from legacy Report Builder

Some features of the legacy Report Builder are not supported, partially supported, or implemented differently in Report Builder:

* **Real-time requests**. Real-time requests are not supported and are removed from the converted legacy workbook.

* **Path/Fallout reporting**. Fall-out requests are not supported and are removed from the converted legacy workbook.

* **[!DNL FTP] option for scheduled reports**. The option to schedule reports to send to an [!DNL FTP] location is no longer available.

* **Publish workbook to [!DNL Power BI] option for scheduled reports**. The option to schedule reports to [!DNL Power BI] is no longer available.

* **Visitors metrics**. The following metrics are converted to *unique visitors* in the converted legacy workbook, even though the reporting result may not be an exact match: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly`, and `visitorsyearly`. This conversion also applies to `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly`, and `mobilevisitorsyearly`.

* **Automatic re-authentication**. When you open a new [!DNL Excel] file, you need to re-authenticate explicitly. This re-authentication is a security feature of [!DNL Office Add-ins] functionality.

* **Copy a worksheet with a group of data blocks**. To support the copy of a worksheet that contains more than one data blocks:
  
  1. Select the worksheet tab in the [!DNL Excel] workbook that you want to copy.
  1. From the context menu of the tab, select **[!UICONTROL Move or Copy...]**
  1. In the **[!UICONTROL Move or Copy]** dialog:
     1. Select where you want the copied worksheet to copy to. 
     1. Ensure you enable **[!UICONTROL Create a copy]**.
     1. Select **[!UICONTROL OK]**.
  1. From the source worksheet: 
     1. Select the cell range that encompasses all data blocks.
     1. Select ![Copy](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]** from the [Report Builder hub](/help/analyze/report-builder/report-builder-hub.md).
  1. In the destination worksheet:
     1. Select the cell where you want the copied cell range to paste to.
     1. Select ![Paste](/help/assets/icons/Paste.svg) **[!UICONTROL Paste data block]** from the [Report Builder hub](/help/analyze/report-builder/report-builder-hub.md).

* **Date range**. Report Builder does not migrate the date range formatting options **[!UICONTROL Show start and end period as]** applied to a row label for a date range in the legacy Report Builder.

* **Average**. Report Builder does not migrate the selected formatting option **[!UICONTROL Average options]** (**[!UICONTROL Daily Average]** up until **[!UICONTROL Yearly Average]**) applied to a metric in the legacy Report Builder. Use a calculated metric to substitute the selected option.

* **Prepend/postpend text**. Report Builder does not migrate the **[!UICONTROL Prepend/postpend text]** applied to a metric in the legacy Report Builder. 
 
* **Subtotals**. Report Builder does not migrate the formatting option **[!UICONTROL SubTotal(this request)]** applied to a metric in the legacy Report Builder. When you have used **[!UICONTROL SubTotal(this request)]** in a legacy workbook request, the functionality is converted to **[!UICONTROL Total]**. For example: in a legacy data block with top 5 page names where you have used **[!UICONTROL SubTotal(Page Views)]** to return the sum of the page views for the top 5 page names. After migration, the same data block with the top 5 page names returns the sum of page views for *all* page names. Use calculated metrics functionality to substitute the legacy **[!UICONTROL SubTotal]** functionality.
