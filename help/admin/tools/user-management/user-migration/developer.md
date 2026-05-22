---
description: Lists APIs affected by the user migration
title: APIs Affected by the user migration
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
    internal-label: User management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# APIs affected by the user migration{#apis-affected-by-the-migration}

Adobe is migrating all Analytics login companies a way from [!DNL my.omniture.com] and onto authentication via the Adobe Experience Cloud. Once a company begins this migration, programmatic user creation and management through the Analytics-specific permissions and `GetLoginKey` methods available via v1.3 and v1.4 of the Analytics Admin API will no longer be supported. Such actions will now be enabled across the Experience Cloud via [!DNL adobe.io].

## API Methods Affected {#methods}

The following API methods in the v1.3 and v1.4 of the Admin API will no longer be supported once you begin user migration:

* Company.GetLoginKey 
* Permissions.AddLogin 
* Permissions.Authenticate 
* Permissions.DeleteGroup 
* Permissions.DeleteLogin 
* Permissions.GetGroup 
* Permissions.GetGroups 
* Permissions.GetLogin 
* Permissions.GetLogins 
* Permissions.GetReportSuiteGroups 
* Permissions.RemoveLoginSegment 
* Permissions.SaveGroup 
* Permissions.SaveLogin 
* Permissions.GetLoginSegment

## Actions You Can Take {#actions}

If your company currently uses these methods, look for a pre-migration notification beginning March 31, 2018. The notification will be sent at least 30 days before your company begins migration to the Experience Cloud authentication, and at that time, these methods will cease to be supported.

If your company does not use any of these methods, no action is required other than ensuring you do not begin using these methods.

For additional information:

* [General User Management Info](https://helpx.adobe.com/enterprise/help/users.html)
* [User Management API Forum](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migration of Analytics User Access and Management to Experience Cloud](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
