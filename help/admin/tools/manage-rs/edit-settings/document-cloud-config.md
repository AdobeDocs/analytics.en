---
description: You can view Document Cloud data in Adobe Analytics
title: Configure Document Cloud reporting
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
TQID: https://experienceleague.adobe.com/2X5YQxmTsMYdnwSWVL4EMr1K1aV9UM6FRMHa2P--Xuc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Configure Document Cloud reporting

You can configure PDF-specific dimensions and metrics to be available in Adobe Analytics. 

## Components added when you enable PDF reporting

When PDF reporting is properly configured, the following dimensions and metrics are available in Adobe Analytics:

**Dimensions:**

* PDF Search Term

* PDF Zoom Level

* PDF Action

* PDF Page Number

* PDF Filename

**Metrics:**

* PDF Views

* PDF Page Views

* PDF Downloads

* PDF Search

* PDF Bookmarks Used

* PDF Copy Text

* PDF Print

## Enable PDF reporting in Adobe Analytics

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **`<select report suite>`** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Document Cloud Management]** > [!UICONTROL **Document Cloud Reporting**].

1. On the Adobe Document Cloud Management page, select [!UICONTROL **Enable PDF Reports**].

1. To configure Adobe Document Cloud to transmit data to Adobe Analytics, use the [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html).
