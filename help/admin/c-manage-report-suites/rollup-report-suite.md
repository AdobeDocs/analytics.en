---
description: Descriptions of report suite types and comparison of global report suites and rollup report suites.
title: Report suite approaches
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
---
# Report suite approaches

<!-- change filename since page name changed? -->

You can configure your report suites as either *global report suites* or *rollup report suites*.

## Global report suites

A global report suite collects data from all domains and apps that your organization owns. It requires implementation to send all image requests to a single report suite.

Adobe recommends implementing a global report suite in most cases. See "[Global report suite considerations](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)" for the advantages of implementing a global report suite.
  
You can provide subsets of your company's global report suite data to different end users using the *multi-suite tagging* and *virtual report suite* approaches:

* **Multi-suite tagging**: Multi-suite tagging allows you to send image requests not only to a global report suite but also to individual child report suites. The global report data is deduplicated across all reports suites.

  For example, you might collect all data in one global report suite and also set up secondary report suites based on brand, region, or another differentiator. The different teams in your company could then focus on data in the report suites that are relevant to them.

  To use multi-suite tagging, implement child report suites and a global report suite that includes all data from the children. The tracking code for your webpages and apps will include the Report Suite ID (RSID) for the global report suite and also the RSIDs for the applicable child report suites.<!-- Wording/be more specific? And include any links? -->
  
  A separate server call is made to each report suite in the image request. The calls to the child report suites are secondary calls.

* **Virtual report suite**: A [virtual report suite](/help/components/vrs/vrs-about.md) is a query on specified segments collected in a global report suite, and available to specified groups of users. Virtual report suites allow you to curate report elements for different end users without using multi-suite tagging, thus avoiding secondary server calls.

  To use virtual report suites, implement a global report suite and then parse the data to create virtual report suites with specific segments applied and with specific group permissions. You can create virtual report suites in the Virtual Report Suite Manager ([!UICONTROL Components] > [!UICONTROL Virtual Report Suites]). See "[Virtual report suite workflow](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)" for more information.

Using virtual report suites instead of multi-suite tagging is often a best practice, but virtual report suites have some limitations. See "[Virtual report suites and multi-suite tagging considerations](/help/components/vrs/vrs-considerations.md)" to determine which report suite approach is the best choice for your business needs. For an in-depth comparison of virtual report suites and multi-suite tagging functionality, see "[Virtual Report Suites vs. Multisuite Tagging](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)."

## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supports rollup reports, and Adobe no longer recommends using rollups. Instead, consider using a global report suite with multi-suite tagging or virtual report suites.

A rollup report is a simple aggregation of data from multiple report suites, without deduplication or any segment or data breakdowns. Rollups do not require code implementation. To use rollup reports, [implement child report suites](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) and then [combine them into a rollup report](/help/admin/c-manage-report-suites/t-rollups.md) using [!UICONTROL Admin Tools].

Rollup reports are free: the child report suites incur their own server calls, but the rollup does not incur additional calls. Rollups are a legacy feature and have many limitations.

### Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups can only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.
