---
title: XDM mapping in the Web SDK upgrade assistant
description: Map your Adobe Analytics variables to fields in an XDM schema as part of a Web SDK migration.
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
# XDM mapping

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="XDM mapping"
>abstract="Map the Analytics variables that you selected to fields in an XDM schema. The upgrade assistant can create a new schema with AI-suggested mappings, or you can map variables to a schema that you already have. Review all mappings before you continue."

<!-- markdownlint-enable MD034 -->

The Web SDK sends data using [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home) fields, so each Analytics variable that you carry forward from [report suite verification](rs-verification.md) needs a matching field in an XDM schema. In this step, you choose a schema and map your variables to its fields.

## Choose a schema {#schema}

You can build the mapping in one of two ways:

* **Create a new schema**: The upgrade assistant analyzes your Analytics variables and suggests an XDM field for each one, then generates a schema from those suggestions for you to review.
* **Use an existing schema**: Select a schema that already exists in Experience Platform, then map each variable to a field yourself.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="Field group preference"
>abstract="Choose which type of field group the upgrade assistant favors when it builds your schema. Standard field groups are defined by Adobe. Custom field groups are defined by your organization."

<!-- markdownlint-enable MD034 -->

When you create a new schema, you also choose whether the upgrade assistant favors standard or custom field groups. Standard field groups are defined by Adobe, while custom field groups are defined by your organization. See [Field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group) in the XDM documentation.

## Review the mapping {#review}

The mapping lists each Analytics variable alongside the XDM field that it maps to, with a preview of the full schema next to it. Select part of the schema to filter the list to the variables that map to it. You can adjust both individual mappings and the schema itself.

The upgrade assistant uses AI to suggest mappings, and the results might not be accurate or complete. Review every mapping before you continue. The upgrade assistant doesn't create the schema in Experience Platform until you [finalize the migration](final-review.md#finalize).

When you're done, select **[!UICONTROL Save and continue]** to save your mapping and go to [Web SDK implementation](web-sdk-implementation.md). To change the mapping after you save it, select **[!UICONTROL Edit]**, make your changes, and then select **[!UICONTROL Save and continue]** again. Changes that you don't save this way aren't included when you finalize the migration.
