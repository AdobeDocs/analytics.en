---
description: Steps that describe how administrators can enable Data Warehouse reporting access to a group of users.
title: Add Data Warehouse user group
feature: Data Warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
exl-id: 8737ab60-2ad1-4795-808b-d0200078a333
---
# Add Data Warehouse user group

Steps that describe how administrators can enable Data Warehouse reporting access to a group of users.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]**.
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. provide the following group information:

   For example, `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. Under [!UICONTROL Tools], enable **[!UICONTROL All Tools]**.

   Alternatively, click **[!UICONTROL Customize]**, then enable **[!UICONTROL Custom Data Warehouse Report]**.

1. Under [!UICONTROL Assign User Logins], add the desired user logins.
1. Click **[!UICONTROL Save Group]**.

   The next time the users added to this group log in, they will see the Data Warehouse option added to the [!UICONTROL Reports & Analytics] menu.

   >[!NOTE]
   >
   >In case of conflicting permissions (such as a user assigned to two groups, one of which denies access to a feature and the other grants that same access), the system restricts permission. Users who belong to groups that deny data warehouse access may need to be removed from those groups.

>[!MORELIKETHIS]
>
>* [Groups](/help/admin/user-management2/c-user-groups/groups.md)
