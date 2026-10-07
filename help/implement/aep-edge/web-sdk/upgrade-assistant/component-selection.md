---
title: Component selection in the Web SDK upgrade assistant
description: Choose which tags rules, data elements, and extensions to include in a Web SDK migration.
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
# Component selection

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="Component selection"
>abstract="Choose the rules, data elements, and extensions to include in this migration. Components that actively contribute to your Adobe Analytics implementation are selected by default. Later steps only work with the components that you select here."

Component selection is the first step of a migration. Use it to choose which rules, data elements, and extensions from your tags property to include in the migration.

The upgrade assistant organizes the components in your tags property into **[!UICONTROL Rules]**, **[!UICONTROL Data Elements]**, and **[!UICONTROL Extensions]** tabs. Each tab lists all of the property's components of that type, based on the snapshot of the library that the upgrade assistant took when you [created the migration](manager.md#create). By default, only the components that actively contribute to your Adobe Analytics implementation are selected. You can select or clear any component.

The **[!UICONTROL Published]** column shows whether each component is part of the library that you selected. Components that aren't part of the library exist in your tags property but not in that library. To filter the list by this, use the **[!UICONTROL Source]** filter.

You can include components that aren't related to Adobe Analytics, such as components for Adobe Target, Adobe Audience Manager, or third-party extensions, but the upgrade assistant doesn't convert them to the Web SDK.

The components that you select determine what later steps work with. For example, you can include data elements that nothing references so that [audit findings](audit-findings.md) can flag them for cleanup.

## View component details {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="Tags usage"
>abstract="The rules, data elements, and extensions that use this component. Extension usage covers extension configuration settings only. Usage inside a rule appears under Rule usage."

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Analytics usage"
>abstract="The Adobe Analytics variables that this component is assigned to, grouped by variable type."

<!-- markdownlint-enable MD034 -->

Select the name of a component to open a panel that shows its configuration and where it's used:

* **[!UICONTROL Tags usage]**: The rules, data elements, and extensions that use the component. **[!UICONTROL Extension usage]** covers extension configuration settings only. Usage inside a rule appears under **[!UICONTROL Rule usage]**.
* **[!UICONTROL Analytics usage]**: The Adobe Analytics variables that the component is assigned to, grouped by variable type.

To see the component in the tags UI, select its name at the top of the panel.

When you're done, select **[!UICONTROL Save and continue]** to go to [audit findings](audit-findings.md).