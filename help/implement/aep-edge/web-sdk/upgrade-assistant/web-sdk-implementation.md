---
title: Web SDK implementation in the Web SDK upgrade assistant
description: Review the Web SDK actions that the upgrade assistant adds to your existing tags rules.
feature: Implementation Basics
role: Admin, Developer, Leader
hide: true
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
# Web SDK implementation

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Web SDK implementation"
>abstract="Review the Web SDK actions that the upgrade assistant adds to your rules. Your Adobe Analytics actions stay in place. Select a component to compare its current and Web SDK configurations side by side. Only the components that you queue are added to the migration."

<!-- markdownlint-enable MD034 -->

Using the components that you selected and your [XDM mapping](xdm-mapping.md), the upgrade assistant adds Web SDK actions to your rules, directly after each Adobe Analytics action. The Analytics actions stay in place, so these rules send data to both Adobe Analytics and the Web SDK. Most data elements carry forward unchanged, and rules continue to reference them by name.

The **[!UICONTROL Change type]** column shows what finalizing the migration does to each component:

* **[!UICONTROL Web SDK actions added]**: The upgrade assistant adds Web SDK actions to the rule.
* **[!UICONTROL No change]**: The component carries forward unchanged.
* **[!UICONTROL Blocked]**: The component needs your review before the upgrade assistant can add Web SDK actions to it. Select the component to see what's blocking it.

Select a component to compare its current configuration with its Web SDK configuration side by side. If you need more context, the upgrade assistant links to the component in the tags UI.

Components that you queue are added to the migration. To queue a component, select it in the list, or select **[!UICONTROL Queue]** in its details. To take it back out, select **[!UICONTROL Remove from queue]**. The upgrade assistant doesn't change your tags property until you [finalize the migration](final-review.md#finalize).

The upgrade assistant uses AI to generate the Web SDK actions, and the results might not be accurate or complete. Generating the actions doesn't verify how they behave on your site, so test them before you publish the library.
