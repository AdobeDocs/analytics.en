---
description: Calculated metrics rights differs between Admin-level users and non-Admins.
title: Role-based rights
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
TQID: https://experienceleague.adobe.com/M2ZwpkhpvhavBOwrVsDxcEYsS9kAFGAcuCl5TSUzxXU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Role-based rights

Calculated metrics rights differs between Admin-level users and non-Admins.

||Create|Share|View/Manage|Approve|Apply|
|--- |--- |--- |--- |--- |--- |
|Admin-level users|Admins can create calculated metrics as well as create Product Profiles in the Admin Console to limit the rights of users to create calculated metrics.|Can share with entire company, with user groups, and with individual users.|Report Builder: Can view/edit/delete/etc. its own calculated metrics and those shared with it.|Can approve calculated metrics as canonical.|Can apply any calculated metrics across the whole organization.|
|Non-Admin-level users|By default, users can create calculated metrics. However, these rights may be limited by Administrators.|Can share with individual users only|Can view/edit/delete/etc. only their own calculated metrics. Non-admin users must have access to all the component events to be able to see a shared metrics (the permissions in the Admin console are still enforced).  If a dashboard or scheduled report is shared with a non-admin user and they don't have the metric shared with them, the report will run with the metric applied (assuming they have permissions to view the events). However, they will not be able to see the definition or edit the metric.|Can only consume approved calculated metrics; cannot mark as approved.|Can apply their own calculated metrics and segments that have been shared with them.|
