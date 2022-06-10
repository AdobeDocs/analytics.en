---
description: The Virtual Report Suite Manager lets Administrators edit, add, tag, delete, rename, approve, copy, export, and filter virtual report suites. It is not visible to non-Admin users.
keywords: Virtual Report Suite
title: Manage virtual report suites
feature: VRS
exl-id: b6d58456-bd07-4d97-aff8-216e8440fdc0
---
# Manage virtual report suites

The Virtual Report Suite Manager lets Administrators edit, add, tag, delete, rename, approve, copy, export, and filter virtual report suites. It is not visible to non-Admin users.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**

![](assets/vrs-manage.png)

>[!NOTE]
>
>In the Virtual Report Suite Manager, you can see only your own virtual report suites. You have to click **[!UICONTROL Show All]** to see everyone else's.

| Task | Description |
| --- | --- |
| Add | Takes you to the virtual report suite builder where you can create new virtual report suites.|
| Tag | All users can create tags for virtual report suites and apply one or more tags to a virtual report suite. However, you can see tags only for those virtual report suites that you own. What kinds of tags should you create? Here are some suggestions for useful tags:<ul><li>Tags based on team names, such as Social Marketing, Mobile Marketing</li><li>Project tags (analysis tags), such as Entry-page analysis</li><li>Category tags: Men's; geography</li><li>Workflow tags: Curated for (a specific business unit); Approved</li></ul>|
| Delete | If you delete a virtual report suite, scheduled reports and dashboards that have this virtual report suite applied continue to work normally. The report or dashboard continues to use the deleted virtual report suite until you re-save the scheduled report.  Scheduled reports do not update when you edit a virtual report suite with the same name.<br>For example: Suppose you have two virtual report suites with the same name and different parent report suites:<br>You have a bookmark that references the virtual report suite for the mainprod report suite. Then you delete that virtual report suite because it's a duplicate. The bookmark continues to run, referencing the definition of the deleted VRS. If you change the definition for the remaining VRS, the VRS applied to the bookmark does not change. It uses the old definition. To fix this, update the bookmark to reference the new definition. If you are unsure whether a bookmark, dashboard or scheduled report is using a deleted VRS, you could change the name of the remaining VRS so it's more clear whether the bookmark is using the remaining VRS.|
| Rename | Everywhere the virtual report suite is displayed, like in the report suite selector, it shows the new name.|
| Approve/Unapprove | Approve virtual report suites to make them "official" or "canonical." You can reverse the process by unapproving.|
| Copy | Creates a distinct copy with its own new report suite ID, but with the same name and definition.|
| Export to CSV | Export the virtual report suite definition to a .csv file.|
| Filter | Filter by tags, parent report suite, owners, and other filters (Show All, Mine, Favorites, and Approved).|
