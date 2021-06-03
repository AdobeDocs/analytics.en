---
description: Outlines the steps to enable your Adobe Analytics implementation to support your data subjects' Data Privacy access and delete rights.
title: Privacy workflow
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
---
# Privacy workflow

This workflow outlines the steps you need to take to make your Adobe Analytics implementation ready to support your data subjects' Data Privacy access and delete rights.

| Task Description | Links to Instructions and More Information |
|--- |--- |
|**Step 1**: Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization.  Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company.|Refer to [Map report suites to an organization](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html).|
|**Step 2**: Set your data retention policy.|A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests.  For more information, see this [Analytics Data Retention FAQ](/help/technotes/data-retention.md).|
|**Step 3**: Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion.|Read these topics in this documentation set:<ul><li>[Data Privacy Labels for Analytics Variables](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Labeling Best Practices](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul>|
|**Step 4**: Assign identity, sensitivity, and data governance labels to each variable in a report suite.  Note:  Remember that Labeling needs to be reviewed each time a new report suite is created or when new variable is enabled within an existing report suite. You may also need to review the labeling when new solution integrations are enabled, as they can expose new variables that may require labeling. A re-implementation of your mobile apps or websites may change the way that existing variables are used, which may also necessitate updates to labels.|Follow the instructions in [Label Report Suite Data](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).|
|**Step 5**: Connect to the Adobe Data Privacy API and submit Access and Delete Requests.|As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API](https://www.adobe.io/apis/experienceplatform/gdpr.html). You can submit any Analytics identifiers (as described in the section [Labeling Best Practices](/help/admin/c-data-governance/gdpr-analytics-ids.md)) in the requests along with their respective namespace IDs (data source IDs).|
|**Step 6**: View and manage your report suite's Data Privacy settings.|Follow the instructions in [View Report Suite's Data Governance Settings](/help/admin/c-data-governance/gdpr-view-settings.md).|
