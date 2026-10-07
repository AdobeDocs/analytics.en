---
title: Web SDK upgrade assistant
description: Plan and execute the migration of your Adobe Analytics tags extension to the Adobe Experience Platform Web SDK.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Web SDK upgrade assistant

The Web SDK upgrade assistant helps you plan and execute the migration of your Adobe Analytics tags extension to the Adobe Experience Platform Web SDK. It brings the migration into a single guided workspace, so you can move from your existing tags implementation to the Web SDK in a structured, trackable way.

## How the upgrade assistant works {#how-it-works}

Each migration works with the Adobe Analytics implementation in one tags property. The upgrade assistant adds Web SDK actions to your existing rules without removing their Adobe Analytics actions, so your implementation continues to send data to Adobe Analytics alongside the Web SDK.

The upgrade assistant converts only Adobe Analytics components. You can include components from other extensions, such as Adobe Target, Adobe Audience Manager, or third-party extensions, but the upgrade assistant doesn't convert them to the Web SDK.

The upgrade assistant guides you through the following steps, and each step builds on the decisions that you make in the previous one:

1. **[Component selection](component-selection.md)**: Choose the rules, data elements, and extensions to include in the migration.
1. **[Audit findings](audit-findings.md)**: Review optional cleanup recommendations for the components that you selected.
1. **[Report suite verification](rs-verification.md)**: Review the Analytics variables in your report suites and choose which ones to carry forward.
1. **[XDM mapping](xdm-mapping.md)**: Map your Analytics variables to fields in an XDM schema.
1. **[Web SDK implementation](web-sdk-implementation.md)**: Review the Web SDK actions that the upgrade assistant adds to your rules.
1. **[Final review](final-review.md)**: Select an Experience Platform sandbox, review what the migration creates, and finalize the migration.

Each step configures part of the migration, and you can return to completed steps to review or change them as often as you want. The upgrade assistant doesn't change your tags property or create anything in Experience Platform until you finalize the migration. When you finalize it, the upgrade assistant creates everything at once and adds the tags changes to a new library. You then test that library and publish it to production using the tags publishing flow.

>[!IMPORTANT]
>
>The upgrade assistant uses artificial intelligence (AI) to generate recommendations, such as XDM field mappings and Web SDK rule configurations. These recommendations might not be accurate or complete. Verify them before you publish your changes to production.

## Prerequisites {#prerequisites}

Before you create a migration, make sure that you have:

* The [permissions](#permissions) that the upgrade assistant requires.
* A tags property that uses the Adobe Analytics extension.
* A library in that property that contains the implementation that you want to migrate. The library can be in any state, including published. See [Libraries](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries) in the Tags user guide.

### Permissions {#permissions}

The upgrade assistant requires the following access. Work with your organization's Experience Platform product admin to get any permissions that you're missing.

| Access type | Required |
| --- | --- |
| [Experience Platform permissions](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL View Schemas]</li><li>[!UICONTROL Manage Schemas]</li><li>[!UICONTROL View Datasets]</li><li>[!UICONTROL Manage Datasets]</li><li>[!UICONTROL View Identity Namespaces]</li></ul> |
| Product access | <ul><li>Data Collection (Tags)</li><li>Adobe Analytics</li></ul> |
| [Tags rights](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL Manage Properties] |

When you're ready, [create a migration](manager.md#create).
