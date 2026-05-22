---
description: Overview of the Advertising Analytics workflow.
title: Workflow overview
feature: Advertising Analytics
exl-id: 00993c19-1e74-4a97-b16a-967feab13b32
TQID: 'https://experienceleague.adobe.com/Xrm-gn59uSRzBKtwY1Z6O40b7d0MS-LH-Y96hLjbJKQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Workflow overview

The workflow of configuring Advertising Analytics consists of the following steps:

<!--
>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/ad-cloud/configuring-advertising-analytics)
-->

1. [Enable Advertising Analytics reporting per report suite](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md). Enables [!UICONTROL Advertising Analytics] reporting for Experience-Cloud-enabled report suites.
2. [Set up an Advertising Analytics account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md). Setup in Analytics Admin Tools.
3. [Report on the Advertising data in Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md). The search data is pulled from search engines around 6AM (06:00) in the time zone of your Adobe Analytics data center. The Adobe Advertising data is collected and inserted into the report suite. And then converted into the report suite time zone as part of inserting the data into Analytics. Reporting is available in Analysis Workspace (Paid Search Performance template), Report Builder, and the Analytics Reporting API.
4. [Manage Advertising accounts](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md). You can check the account status, and edit/pause accounts.
