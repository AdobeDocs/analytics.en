---
description: Project sharing and project roles in Workspace
keywords: Analysis Workspace sharing
title: Share projects
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
---
# Share projects

You can share an Analysis Workspace project with the following types of people:

* Users and groups in your organization who have access to Adobe Analytics

* Users and groups in your organization who don't have access to Adobe Analytics

* People outside your organization

Any [curation](curate.md) you apply prior to sharing is reflected when recipients open the project. 

Here is a video overview of project sharing:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Share with Adobe Analytics users and groups in your organization {#Add}

You can share a project with existing Adobe Analytics users or groups in your organization. When you share a project as described in this section, the users you share with must already have an Adobe Analytics account.

You can share a specific role with users or groups, or you can share a link.

* [Share a specific project role](#share-a-specific-project-role)

* [Share a link to a project](#share-a-link-to-a-project)

### Share a specific project role

When sharing a specific project role with users and groups in your organization, consider the following:

* Project roles (**[!UICONTROL Can edit]**, **[!UICONTROL Can duplicate]**, and **[!UICONTROL Can view]**) are tied to the user and specific project ID. Project roles are independent of user permissions managed in the [Adobe Experience Cloud admin console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).
   
* In Adobe Analytics, groups are defined by product profiles in the [Adobe Experience Cloud admin console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html). Admins can share to any group, including "All." Non-admins can share to any group they are a member of, with the exception of "All."

* A user who is placed in multiple roles always get the highest experience. This might occur if a user is added both as an individual and as part of a group. For example, if a user is given the **[!UICONTROL Can edit]** role as an individual and the **[!UICONTROL Can view]** role as a member of a group, they will receive a **[!UICONTROL Can edit]** project experience.

* Admins placed in the **[!UICONTROL Can duplicate]** or **[!UICONTROL Can view]** role receive those limited experiences when they open a project. If desired, an Admin can increase their role to **[!UICONTROL Can edit]** at anytime through **[!UICONTROL Components] > [!UICONTROL Projects]**. 

To share a specific project role with users or groups in your organization:

1. Go to the project that you want to share, then click **[!UICONTROL Share]** > **[!UICONTROL Share project]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
   If there are unsaved changes, you are prompted to save your project first. 

   ![](assets/share-proj-modal.png)

   For information about how to share multiple projects simultaneously, see [Share projects in the Project manager](#share-projects-in-the-project-manager).

1. Add recipients or groups of recipients in one of the provided role fields:

   **Can edit:** Recipients can **[!UICONTROL Save]** changes to a project and function as co-owners. This role is useful if you want to co-manage a project with other colleagues; this includes editing, deleting, and modifying recipient lists for a shared project. <br>Note: Analysis Workspace does not currently support live collaboration, so it is recommended that only one user edit a project at a given time. If projects are saved at the same time, the last version will be kept. 

   **Can duplicate:** Recipients can **[!UICONTROL Save as]** and have access to the left rail. Project interactions are not limited in this role. This role is useful if you want to share a project to users who understand your organization's data and how to use Analysis Workspace, but you do not want your project altered.

   **Can view:** Recipients cannot **[!UICONTROL Save]** or **[!UICONTROL Save as]** and do not have access to the left rail. Project interactions are also limited. This role is useful if you want to share a project to users that are less familiar with your organization's data structure, Analysis Workspace or Adobe Analytics generally. However, you still want them to consume data and insights in a safe environment. Learn more about the [Can view project experience](/help/analyze/analysis-workspace/curate-share/view-only-projects.md).

1. Choose whether to enable the following options when sharing the project:

   * **Share embedded project components:** Shares segments, calculated metrics, and date ranges with all recipients. After being shared, these components will appear in the Components drop-down of the recipient's Workspace. This setting does not persist - it is a one-time action at the time of sharing.

   * **Set as landing page for recipients:** Sets this page as the landing page for recipients. This setting does not persist - it is a one-time action at the time of sharing.
 
1. Click **[!UICONTROL Share]**. 
  You can also click **[!UICONTROL Curate and Share]** to apply project curation automatically. If a project has already been shared, these buttons will say **[!UICONTROL Update]** and **[!UICONTROL Curate & Update]**. Learn more about [project curation](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html).

### Share a link to a project 

When sharing a link as described in this section, consider the following: 

* Recipients who use the link are required to log in to Adobe Analytics before gaining access to the project. 

* If a recipient is not assigned a role and receives a [link](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) to the project (**[!UICONTROL Share] > [!UICONTROL Get project link]**), they are given a role by default. Admins receive **[!UICONTROL Can edit]** and Non-admins receive **[!UICONTROL Can duplicate]**.

To share the project link with users in your organization:

1. Click **[!UICONTROL Share]** > **[!UICONTROL Share project]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
   If there are unsaved changes, you are prompted to save your project first. 

   ![](assets/share-proj-modal.png)

1. Click **[!UICONTROL Copy link]** next to the **[!UICONTROL Share URL field]**. 

1. Share the link with users in your organization. For example, you can paste it into an email, onto an internal web site, and so forth. 

## Share a public link with anyone (no login required) {#share-public-link}

You can share Analysis Workspace projects with people who don't have access to Adobe Analytics. This can include:

* People outside your organization 

* People within your organization who are not provisioned with Adobe Analytics  

>[!NOTE]
>
>This option can be disabled by the Analytics administrator, as described in [Preferences](/help/analyze/analysis-workspace/user-preferences.md). If you can't share a public link as described in this section, your Analytics administrator has disabled this ability.

To share a public link to an Analysis Workspace project:

1. Open the Analysis Workspace project that you want to share.

1. Click **[!UICONTROL Share]** > **[!UICONTROL Share public link]**.
   
   If there are unsaved changes, you are prompted to save your project. 

   <!-- Add screen shot of new modal -->

1. Enable the **[!UICONTROL Link active]** option if it is not already enabled.

1. Choose whether to enable the following security options (these options can be controlled by your Analytics administrator): 

   * **[!UICONTROL Require single sign-on (SSO) authentication]:** 
   
     Require people with the link to authenticate via SSO prior to gaining access to the shared project. Select this option if you want the project to be accessible only to users within your organization.

     Analytics administrators can set this preference for the company, as described in [Preferences](/help/analyze/analysis-workspace/user-preferences.md). You might encounter the following scenarios, depending on how the administrator configured this option:
     
     * If this option is not visible, either SSO is not enabled for your organization or your Analytics administrator did not enable this feature. 

     * If this option is enabled and dimmed, your Analytics administrator requires SSO authentication in order to access all public links. 
   
   * **[!UICONTROL Require Password]:** Require people with the link to specify a password prior to accessing the Analysis Workspace project. This provides an additional level of security to your project.
   
     If you select this option, specify a password. Remember to share this password along with the project link when you share it with others. <!--go through this workflow and see how it works.-->

     If this option is enabled and dimmed, your Analytics administrator requires all public links to be password protected. Analytics administrators can set this preference for the company, as described in [Preferences](/help/analyze/analysis-workspace/user-preferences.md).

1. Next to the **[!UICONTROL Share with anyone (no login required)]** field, click the **Copy link** icon to copy the link to your system clipboard. 

1. Share the link with the people you want to have access to the project. For example, you can paste the link as send it in an email. 
   
   Any person you share the link with can view the Analysis Workspace project. If you chose to require a password, you must also share the password with anyone you want to access the link.

1. Select **[!UICONTROL Close]** to close the share dialog box. Your changes are automatically saved. <!-- True? -->


## Share projects in the Project manager {#Manager} 

Projects can also be shared from **[!UICONTROL Components] > [!UICONTROL Projects]**. A single project can be shared following the same steps above.  If multiple projects are selected to be shared, recipients will be added to the existing list of recipients for each project. 

For example: 

* Project A is shared to recipients  1, 2, 3 
* Project B is shared to recipients 4, 5, 6 

With Project A and B selected, recipients 4 and 7 are added to the share lists. The new share list for each project is now: 

* Project A: 1, 2, 3, 4, 7 
* Project B: 4, 5, 6, 7 

![](assets/mult-proj-sharing.png)

## Share embedded components

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## FAQs {#FAQs}

| Question | Answer |
| --- | --- |
| What happens if two editors save a project at the same time? | Changes are not merged and the last saved project version will be kept. Analysis Workspace does not currently support live collaboration. |
| As an admin, what project experience will I see? | Admins placed in a **[!UICONTROL Can duplicate]** or **[!UICONTROL Can view]** role will receive those limited experiences when they open a project. If desired, an Admin can increase their role to **[!UICONTROL Can edit]** at anytime through **[!UICONTROL Components] > [!UICONTROL Projects]**. |
| What happens if a recipient is placed in one role as an individual and another role as a member of a group? | If a recipient is placed in multiple roles, they will always receive the higher experience. For example, if a recipient is given the **[!UICONTROL Can edit]** role as an individual and the **[!UICONTROL Can view]** role as a member of a group, they will receive a **[!UICONTROL Can edit]** project experience. |
| What experience does a recipient get if they open a project link? | Recipients receive the role you placed them in the share modal. If a recipient is not assigned a role and receives a link to the project (**[!UICONTROL Share] > [!UICONTROL Get project link]**), they will be placed into a role by default. Admins receive **[!UICONTROL Can edit]** and Non-admins receive **[!UICONTROL Can duplicate]**. |
