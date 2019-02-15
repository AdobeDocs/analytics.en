---
description: These changes to the way calculated metrics work in Analytics may impact you.
seo-description: These changes to the way calculated metrics work in Analytics may impact you.
seo-title: Frequently Asked Questions
title: Frequently Asked Questions
uuid: 9b7f1cd1-b969-4b15-8af1-969d816b65b8
---

# Frequently Asked Questions

These changes to the way calculated metrics work in [!DNL Analytics] may impact you.

 [1. How do I access the Calculated Metric Builder?](../../components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[2. How do I access the Calculated Metric Manager?](../../components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[3. Why do I see so many Calculated Metrics with the Same Name?](../../components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[4. What happened to my Global Calculated Metrics?](../../components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[5. What happened to Global Calculated Metrics that were shared across Login Companies?](../../components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[6. What happened to Calculated Metrics with a Numeric or Numeric2 Classification?](../../components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[8. What happened to Life-Time Metrics?](../../components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[9. What do I need to know about Calculated Metrics based on Daily/Weekly/Monthly/Quarterly/Yearly Unique Visitor metrics?](../../components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[10. What about Calculated Metrics created or managed with the old report suite API methods?](../../components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[11. Does Current Data Does support all types of Calculated Metrics?](../../components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[12. What does "No name provided" mean in conjunction with migrated calculated metrics?](../../components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[13. What happens to a user's calculated metrics if that user was deleted?](../../components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[14. Why do I see “Unknown" calculated metrics that aren't 'valid' for other report suites even though they can be created and applied to those report suites?](../../components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[15. Why were changes that I made to my legacy calculated metrics not saved?](../../components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[16. Why don’t my calculated metrics show up in the Marketing Channels report?](../../components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[17. Why do some of the calculated metrics show formulas without the parentheses I added?](../../components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[18. (Ad Hoc Analysis only) Are Calculated Metrics with Embedded or Inline Segment Definitions still supported?](../../components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[19. (Report Builder only) Why have calculated metrics disappeared from my requests?](../../components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[20. How do Calculated Metrics Totals work?](../../components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## Step 1. How do I access the Calculated Metric Builder? {#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Click **[!UICONTROL + Add]** at the top of the Calculated Metric Manager, or 
* In any Analytics report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Add]**.

## Step 2. How do I access the Calculated Metric Manager? {#section_DD0BD13E9EC940268EBE8BC88241A152}

* Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Components]** in the left navigation. Then click **[!UICONTROL Calculated Metrics]**. 

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## Step 3. Why do I see so many Calculated Metrics with the same name? {#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(Previously, global calculated metrics were not owned by any specific Admin user and were visible to all users of that report suite. The metrics were segregated by report suite. If a metric in one report suite had the same name as a metric in a different report suite, it would simply appear to users as the same metric when they switched report suites.)

Now, metrics are no longer segregated by report suites. If a metric in one report suite had the same name as a metric in a different report suite, they will both be visible in the Calculated Metric Builder as well as the Metric Selector and might appear as duplicate metrics even though they may or may not have the same definition.

You would see a number of calculated metrics with the same name (but created in different report suites) only if you unchecked the (Only `<report suite>`) checkbox as shown here:

  ![](assets/report_suite.png)

**What You Need to Do**

Consider consolidating calculated metrics with similar names and definitions but exercise caution when doing so. You can check the report suite for a calculated metric in the Calculated Metric Manager to verify its original report suite. You should also check the definitions of metrics when deleting potential duplicates to ensure that you are correctly consolidating metrics.

>[!NOTE]
>
>Even though calculated metrics are no longer bound to a specific report suite and can be used across any report suite that is visible to the login company, the report suite under which the calculated metric was created or last saved is still visible in the Calculated Metric Manager.

>[!NOTE]
>
>Even if a Calculated Metric is deleted, any bookmarks or dashboard reports that reference that metric will still function.

## Step 4. What happened to my Global Calculated Metrics? {#section_7351D4C7361F4ABAA1B43F8E89AAD211}

(Previously, an Admin could create calculated metrics (known as "global calculated metrics" or "report suite calculated metrics") in a Report Suite via Admin Tools.

Global calculated metrics are now owned by the first Admin user in the login company's list of Admin users. They will be shared with "Everyone" by default. This pattern follows the same sharing model and migration plans as segments.

**What You Need to Do**

Nothing. However, the new Admin owner should exercise caution when modifying or deleting these calculated metrics - they may be used in a number of bookmarked reports and dashboards.

>[!NOTE]
>
>Even if a Calculated Metric is deleted, any bookmarks or dashboard reports that reference that metric will still function.

## Step 5. What happened to Global Calculated Metrics that were shared across Login Companies? {#section_59E5CD948ED643AE9AD3D2E4277647F8}

(Previously, an Admin could create calculated metrics (known as "global calculated metrics" or "report suite calculated metrics") in a Report Suite via Admin Tools. These metrics could then be "shared" across login companies by adding the report suite to multiple login companies.)

Global calculated metrics can no longer be shared across login companies. They are no longer bound or tied to a specific report suite but are instead tied to a specific login company. Calculated metrics that were shared across login companies

* Were migrated to all the login companies with access to that report suite. 
* Default to "shared with Everyone". 
* Will be copies independent from all the other login companies.

>[!NOTE]
>
>If the calculated metric was used in a bookmark, dashboard, alert, or scheduled report, editing the new copy will NOT affect the old persisted calculated metric.

## Step 6. What happened to Calculated Metrics with a Numeric or Numeric2 Classification? {#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs. However, they will not be supported in any report with a segment applied.

In addition, calculated metrics with a Numeric or Numeric2 classification will not be supported in the following components: [!UICONTROL Ad Hoc Analysis], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] reports, [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis]. When you create or edit a calculated metric with a Numeric or Numeric2 classification, you will see a compatibility warning that the calculated metric is not compatible with certain areas of the product.

**What You Need to Do**

Avoid creating calculated metrics with Numeric1 or Numeric2 classifications if the metric is intended to be used with a segment or with any of the non-compatible components.

## Step 7. What happened to Life-Time Metrics? {#section_AEDB02EF24584DAD8731BED9DDCE4F48}

Life-Time metrics (a.k.a. all-time metrics) are no longer supported and no longer visible in the [!UICONTROL Reports & Analytics] UI or any other UI. They cannot be queried by the Report API.

Any bookmarks, dashboards, scheduled reports, or alerts that contained an all-time metric will continue to run without that metric as long as at least one other valid metric is also on the report. If the only metric on the bookmark, dashboard, scheduled report, or alert is an all-time metric, the report will no longer run.

## Step 8. What do I need to know about Calculated Metrics based on Daily/Weekly/Monthly/Quarterly/Yearly Unique Visitor metrics? {#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and Reporting API.

However, these metrics will not be supported in the following components: [!UICONTROL Segments], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] reports, [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis]. When you create or edit a calculated metric based on Unique Visitors metrics, you will see a compatibility warning that the metric is not compatible with certain areas of the product.

You use a base Unique Visitor metric on a report with a segment. You can create a Calculated Metric based on a Unique Visitor metric; however, that calculated metric cannot be applied to a report with a segment, nor can that calculated metric have a segment embedded in it.

## Step 9. What happens to Calculated Metrics created or managed with the old report suite API methods? {#section_13ED1BAD02634674BDAEB479B060A4B6}

Previously, saving a calculated metric with the (1.3 or 1.4) API method ReportSuite.SaveCalculatedMetrics was the same as creating or updating a calculated metric in the Admin Console. The same applied to ReportSuite.DeleteCalculatedMetrics. Also, the list of calculated metrics displayed in the Admin Console or when calling ReportSuite.GetCalculatedMetrics was the same.

Now, the ReportSuite CalculatedMetrics API methods (1.3 or 1.4) will continue to save, delete and retrieve calculated metrics using the old store. Existing calculated metrics will be migrated over and will be visible in the new Calculated Metrics Builder. **New calculated metrics created with the API methods will be visible only in the API. They will still be usable in the Reporting API.**

**What You Need to Do**

If you need to use both the API and the Calculated Metric Builder, you should stop using the ReportSuite CalculatedMetrics API methods and instead use the new CalculatedMetrics API methods (Get, Save, Delete and GetFunctions).

## Step 10. Does Current Data support all types of Calculated Metrics? {#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

Current data does not support calculated metrics that contain segments or statistical functions. The only functions that are supported are basic mathematical functions like addition, deletion, multiplication, division, and negation (-x).

## Step 11. What does "No name provided" mean in conjunction with migrated calculated metrics? {#section_C90CBB72A67644F38D583301981F8D03}

"No name provided" means that no metric name is associated with this migrated metric (just a formula without a descriptive name).

## Step 12. What happens to a user's calculated metrics if that user was deleted? {#section_42ED4C15830540879C4A161423690E5A}

Any calculated metrics that this user created are also deleted. However, deleted calculated metrics will still work as part of saved bookmarks, dashboards, or scheduled reports.

## Step 13. Why do I see “Unknown" calculated metrics that aren't 'valid' for other report suites even though they can be created and applied to those report suites? {#section_6772818EFDED46E9B7095D64C3B77211}

The user interface displays “unknown” if the calculated metric contains base metrics or dimensions that don’t exist for the selected report suite.

## Step 14. Why were changes that I made to my legacy calculated metrics not saved? {#section_81CDEFCA1FD542579AF183DA1494EAF0}

This might be due to the timing of the migration to the new calculated metric database, which took place between June 15 and June 18, 2015.

**What You Need to Do**

You will have to redo the changes you made to your legacy metrics.

## Step 15. Why don’t my calculated metrics show up in the Marketing Channels report? {#section_FC350359A775433AB5F43C7CAB304D62}

(Previously, all calculated metrics were listed in the metric selector on Marketing Channels reports with a First Touch and Last Touch option.)

Now, only those calculated metrics that have their allocation type specifically set to First Touch or Last Touch in the Calculated Metrics builder will be available in the metric selector on Marketing Channels reports. Note that any calculated metrics already applied to Marketing Channel reports will continue to be applied and work as they did before. To create a calculated metric for Marketing Channels, click the configuration icon in the metric builder and select either First Touch or Last Touch as the allocation type. Remember that doing this will make the calculated metric compatible only with Marketing Channel reports and it won’t be usable on any other report.

## Step 16. Why do some of the calculated metrics show formulas without the parentheses I added? {#section_AC0D1E9714AD487F9A1C73359F518B5E}

During the migration, Adobe stripped out superfluous parentheses from some formulas. Only parentheses that do not affect how the metric is calculated were removed. This won’t change the data - it just simplifies the formula.

## Step 17. (Ad Hoc Analysis only) Are Calculated Metrics with embedded or inline segment definitions still supported? {#section_B25C924A282F49388AB604E3D826F44C}

Calculated metrics created in Ad Hoc analysis could previously contain inline segment definitions. This is no longer possible.

**What You Need to Do**

You need to explicitly save the segment. Existing calculated metrics with inline segment definitions will continue to run correctly and can be viewed in Ad Hoc Analysis, but they cannot be saved without explicitly saving the segment.

## Step 18. (Report Builder only) Why have calculated metrics disappeared from my requests? {#section_DA4792FE5D7945218CD5E6328DE08E82}

If the request was created in v5.2 and it contains calculated metrics, those metrics are not visible in v5.1 (or earlier versions). This is because calculated metrics now use Global IDs (non report-suite-specific IDs).

**What You Need to Do**

You need to upgrade to v5.2 to be able to see these metrics.

## Step 19. How do Calculated Metrics Totals work? {#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports & Analytics] shows a calculated metrics total in [!UICONTROL Reports & Analytics], it's just applying the formula to the total. For example, the total for the calculated metric Orders/Visit takes the Total Orders and divides them by the Total Visits. In some cases, however, the calculated metric total is not just the sum of line items, but a total for the site.

Example 1: Visitors for a search term: the same visitor may have searched for multiple terms, so in this case, total visitors do not equal the sum of the line items.

Example 2: Page views on products: in the cart, there may be multiple products, so as a result, there are multiple page views for the cart. For more information on comparing the sum of line items to report totals, see [this knowledge base article](https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/sum-line-items-different-from-total.html). 
