---
description: Calculated metrics rights differs between Admin-level users and non-Admins.
title: Role-based rights
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
---
# Role-based rights

Calculated metrics rights differs between Admin-level users and non-Admins.

||Create|Share|View/Manage|Approve|Apply|
|--- |--- |--- |--- |--- |--- |
|Admin-level users|Admins can create calculated metrics as well as create Product Profiles in the Admin Console to limit the rights of users to create calculated metrics.|Can share with entire company, with user groups, and with individual users.|Report Builder: Can view/edit/delete/etc. its own calculated metrics and those shared with it.|Can approve calculated metrics as canonical.|Can apply any calculated metrics across the whole organization.|
|Non-Admin-level users|By default, users can create calculated metrics. However, these rights may be limited by Administrators.|Can share with individual users only|Can view/edit/delete/etc. only their own calculated metrics. Non-admin users must have access to all the component events to be able to see a shared metrics (the permissions in the Admin console are still enforced).  If a dashboard or scheduled report is shared with a non-admin user and they don't have the metric shared with them, the report will run with the metric applied (assuming they have permissions to view the events). However, they will not be able to see the definition or edit the metric.|Can only consume approved calculated metrics; cannot mark as approved.|Can apply their own calculated metrics and segments that have been shared with them.|
