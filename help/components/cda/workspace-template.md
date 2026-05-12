---
title: CDA Workspace template
description: Describes each field in the CDA template within Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/Zui1m27pi3eQnm-dac2akfGRF01IbPaQ0SwLD01iDAE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
    internal-label: Experimentation
---
# CDA Workspace template

{{available-existing-customers}}

Adobe offers a template to see vital cross-device performance data.

1. Navigate to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) and log in using your AdobeID credentials.
1. Click the 9-grid icon at the top, then click Analytics.
1. Click [!UICONTROL Workspace] at the top, then click [!UICONTROL Create New Project].
1. Locate the "Cross-Device Analysis" template, then click [!UICONTROL Create].
1. If prompted, change the report suite to one that supports CDA.

An Analysis Workspace project is created that contains several panels. At the top, a table of contents and introduction is shown, allowing context to the report and navigation to individual reports. Click a link within the table of contents or expand a panel's accordion to view those reports.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identification of users**: Shows how often visitors to your site are identified using methods based on Cross-Device Analytics.
* **Measuring audience size**: Shows a comparison of 'Unique Devices' compared to 'People'. The proportion of these two numbers is known as 'Cross-device compression', a calculated metric visible in this panel. This compression metric depends on a broad range of factors:
  * Log in rate: The more users log in on your site, the more Adobe can identify and stitch visitors across devices. Sites with a low log in rate also have low compression rates.
  * Experience Cloud ID coverage: Only visitors with an ECID can be stitched. A lower percentage of visitors to your site using an ECID correlates to lower compression rates.
  * Multiple device usage: If visitors to your site don't use multiple devices, you can see lower compression rates.
  * Reporting granularity: Compression by day is typically smaller than compression by month or year. The chances for an individual to use multiple devices becomes smaller within a single day than over an entire month. Segmenting, filtering, or using breakdown dimensions can also show a lower compression rate.
* **People-based segments**: Contains a segment drop-down list that allows you to view device specific data. This panel encourages experimentation with segments to see how including or excluding device types affect reports.
* **Analyzing the cross-device journey**: Provides flow and fallout reports based on device type.
* **Cross-device attribution**: Combine the features of cross-device analytics and attribution together.
* **Other tips and tricks**: Helpful topics around CDA that lets you get more out of using it.
