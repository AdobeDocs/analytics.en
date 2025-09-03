---
description: Lists APIs affected by the user migration
title: APIs Affected by the user migration
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
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
* [Migration of Analytics User Access and Management to Experience Cloud](/help/admin/admin/user-management2/user-migration/c-migration-tool.md)
