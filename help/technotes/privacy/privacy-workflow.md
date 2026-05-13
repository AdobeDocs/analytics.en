---
description: Outlines the steps to enable your Adobe Analytics implementation to support your data subjects' Data Privacy access and delete rights.
title: Privacy workflow
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Privacy workflow

This workflow outlines the steps you need to take to make your Adobe Analytics implementation ready to support your data subjects' Data Privacy access and delete rights.

1. Start with the [Privacy Service overview](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) page in Adobe Experience Platform to get an idea of what questions to ask before you label your Analytics data.
1. **Set your data retention policy.** A data retention policy is required for Adobe to service Data Privacy data access/delete requests.  For more information, see the [Data Retention FAQ](/help/technotes/data-retention.md). In order to use the Privacy Services API, you must ensure that the data retention period is set within Adobe Analytics.
1. **Familiarize yourself with Data Privacy labels, Adobe Analytics IDs, and namespaces.** See [Data Privacy Labels for Analytics Variables](/help/admin/tools/privacy-labeling/labels.md) and [Labeling Best Practices](/help/admin/tools/privacy-labeling/best-practices.md).
1. **Assign identity, sensitivity, and data governance labels to each variable in a report suite.** Labeling needs to be reviewed each time a new report suite is created or when new variable is enabled within an existing report suite. Also review the labeling when new solution integrations are enabled, as they can expose new variables that may require labeling. A re-implementation of your mobile apps or websites can change the way that existing variables are used, which can also necessitate updates to labels. See [Label Report Suite Data](/help/admin/tools/privacy-labeling/namespaces.md).
1. **Connect to the Adobe Data Privacy API and submit Access and Delete Requests.** As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html). You can submit any Analytics identifiers (as described in the section [Labeling Best Practices](/help/admin/tools/privacy-labeling/best-practices.md)) in the requests along with their respective namespace IDs (data source IDs).
1. **View and manage your report suite's Data Privacy settings.** See [View Report Suite's Data Governance Settings](/help/admin/tools/privacy-labeling/view-settings.md).
