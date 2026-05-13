---
description: Describes how to run the Marketing Channel report, grant limited admin user rights, and user group permissions to report.
title: Marketing Channel permissions
feature: Marketing Channels
exl-id: 3b3bcf9b-eee7-4d84-9d4a-e4a24e0cdd4d
TQID: https://experienceleague.adobe.com/X7-0WVqyY5qjzQh3OJ7eE3-OXD7wvY6-gdqY7FMS9jA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Marketing Channel permissions

>[!NOTE]
>
>To maximize effectiveness of Marketing Channels for Attribution and Customer Journey Analytics, we have published some [revised best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Analytics administrators can manage marketing channels for their organizations as described in [Manage Marketing Channels](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Here are the Report Suite Tools permissions needed in the [Admin Console](https://adminconsole.adobe.com/) to be able to work with various aspects of Marketing Channels.

|Permission type|Permission name|Description|
|---|---|---|
|Report Suite Tools|Channels|Grants access to Marketing Channels, including Marketing Channel Manager, Marketing Channel Processing Rules, and Marketing Channel Expiration in the Report Suite Manager.|
|Report Suite Tools|Costs|Grants access to Marketing Channels > Marketing Channel Costs in the Report Suite Manager.|
|Report Suite Tools|Classifications|Grants access to all classification settings in the Report Suite Manager, including Marketing Channels > Marketing Channel Classifications.|
|Analytics Tools|Analysis Workspace Access|Grants access to Analysis Workspace. Users must belong to either this group (preferred) or Reports &and  Analytics Access to use the Marketing Channels dimensions in Workspace.|
|Analytics Tools|Reports and Analytics Access|Grants access to Reports and Analytics. Users must belong to either this group or Analysis Workspace Access (preferred) to use Adobe Analytics.|

For more information on product profiles and Adobe Analytics permissions in Admin Console, see [Product profiles for Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).

