---
description: You can protect all requests in a workbook against adding and editing requests by locking the workbook. This enables offline editing of workbooks by pausing all report requests for more efficient editing.
title: Lock/unlock workbooks
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
feature: Report Builder
role: User, Admin
exl-id: b5a83532-9fa7-4f1f-b744-e5d74781fffb
---
# Lock/unlock workbooks

You can protect all requests in a workbook against adding and editing requests by locking the workbook. This enables offline editing of workbooks by pausing all report requests for more efficient editing.

As an analyst, locking a workbook lets you protect your workbook requests against tampering by other users within your organization. At the same time, those users can still refresh the requests in the workbook.

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)).

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)).

You can unlock a locked workbook if you have one of the following permissions:

* You are an administrator, or 
* You are the person who initially locked the workbook. In this case, you do not have to be an administrator.

>[!NOTE]
>
>You cannot add a request to a protected workbook unless you have the permissions to unlock the workbook.

When a workbook is locked against request editing,

* Users cannot create/add requests.
* Users cannot edit requests through the Request Wizard.
* Users cannot edit requests through the Edit Multiple Request features.
* Users cannot cut, copy or paste requests. However, users can still use the native Excel Cut/Copy/Paste context menu to cut/copy/paste the content of the request(s).
* Users can refresh requests, either individually or as a part of a group.
* If the request uses input values from cells (date range, segment, filters), users can change these values in the cells, and thus indirectly edit the requests by refreshing them.

If you try to edit a protected workbook (through the context menu, or **[!UICONTROL Request Manager]**, or **[!UICONTROL Edit Multiple Requests]**), you may or may not be allowed to do so:

* If you do not have permissions to unlock the request(s), this prompt appears:

  ![](assets/locked_workbook_error.png)

* If you have the required permissions, no prompt is shown, and you can edit the request.

## Workflow {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Let's assume workbook A has one request which is in a locked state and was created by User A.

**Example 1: Admin user (or User A)**

1. User logs into Report Builder and opens workbook A.
1. Workbook A is currently locked, so the "Create Request" button is deactivated in the toolbar, along with all other buttons whose functionality is disabled by locking.
1. If the user attempts to use one of the deactivated buttons, a message appears that the workbook is currently locked.
1. The user may unlock the workbook, which enables full editing functionality.
1. After unlocking, the workbook remains unlocked until explicitly re-locked.

**Example 2: Non-Admin user (User B)**

1. User logs into Report Builder and opens workbook A.
1. User cannot add/edit the request.
1. User cannot unlock the workbook.
