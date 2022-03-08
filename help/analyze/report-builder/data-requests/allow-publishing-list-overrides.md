---
description: When you schedule a report, you can choose a publishing list to use for distribution.
title: Allow Publishing List Overrides
feature: Report Builder
role: User, Admin
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
---
# Allow Publishing List Overrides

When you schedule a report, you can choose a publishing list to use for distribution.

Publishing lists are set up in Analytics Admin tools.

See [Publishing List Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html) in the Analytics Reference.

To enable this feature, navigate to the [!UICONTROL Request Wizard: Step 1] window.

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. In addition, if the workbook contains several report suites, the report suite ID associated to the publishing list is used.

This option is not available for report suites that you select from cells.

>[!NOTE]
>
>If you send the scheduled report to multiple publishing lists, the report runs once for each list. Variable report suites are replaced by the report suite assigned to the publishing list.
