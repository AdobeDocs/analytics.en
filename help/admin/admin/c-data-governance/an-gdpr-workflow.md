---
description: Outlines the steps to enable your Adobe Analytics implementation to support your data subjects' Data Privacy access and delete rights.
title: Privacy workflow
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
---
# Privacy workflow

This workflow outlines the steps you need to take to make your Adobe Analytics implementation ready to support your data subjects' Data Privacy access and delete rights.

1. Start with the [Privacy Service overview](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) page in Adobe Experience Platform to get an idea of what questions to ask before you label your Analytics data.
1. **Set your data retention policy.** A data retention policy is required for Adobe to service Data Privacy data access/delete requests.  For more information, see the [Data Retention FAQ](/help/technotes/data-retention.md). In order to use the Privacy Services API, you must ensure that the data retention period is set within Adobe Analytics.
1. **Familiarize yourself with Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion.** See [Data Privacy Labels for Analytics Variables](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) and [Labeling Best Practices](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion.** See [Data Privacy Labels for Analytics Variables](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md) and [Labeling Best Practices](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Assign identity, sensitivity, and data governance labels to each variable in a report suite.** Labeling needs to be reviewed each time a new report suite is created or when new variable is enabled within an existing report suite. Also review the labeling when new solution integrations are enabled, as they can expose new variables that may require labeling. A re-implementation of your mobile apps or websites can change the way that existing variables are used, which can also necessitate updates to labels. See [Label Report Suite Data](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).
1. **Connect to the Adobe Data Privacy API and submit Access and Delete Requests.** As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html). You can submit any Analytics identifiers (as described in the section [Labeling Best Practices](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)) in the requests along with their respective namespace IDs (data source IDs).
1. **View and manage your report suite's Data Privacy settings.** See [View Report Suite's Data Governance Settings](/help/admin/admin/c-data-governance/data-labeling/gdpr-view-settings.md).
