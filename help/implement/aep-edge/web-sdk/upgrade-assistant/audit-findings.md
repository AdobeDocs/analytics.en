---
title: Audit findings in the Web SDK upgrade assistant
description: Review and resolve optional cleanup recommendations for your tags components before you migrate to the Web SDK.
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
# Audit findings

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="Audit findings"
>abstract="Findings point out rules and data elements that you might want to clean up before you migrate, such as data elements that nothing references. Accept a finding to include its recommended change in the migration, or decline it to leave the component as it is. This step is optional."

<!-- markdownlint-enable MD034 -->

The upgrade assistant checks the rules and data elements that you selected in [component selection](component-selection.md) and flags ones that you might want to clean up before you migrate:

* Duplicate rules, or rules that share events and conditions, that you could consolidate
* Rule action sequences that could affect data accuracy
* Duplicate data elements that you could consolidate
* Data elements that might be unused, which you could disable

This step is optional. You can resolve as many findings as you want, or continue directly to [report suite verification](rs-verification.md).

## Review a finding {#review}

Select a finding to see its details, including:

* A description of the finding
* The component's current configuration
* Where the component is used, both in your tags property and in Adobe Analytics

Each finding includes a recommended action, which depends on the type of finding. For example, the recommended action for a data element that nothing references is to disable it.

>[!IMPORTANT]
>
>A data element that's flagged as unused might still be referenced dynamically, or from outside of tags. Before you accept a finding, check its proposed changes, custom code, action order, and references to confirm that they keep the behavior that you intend.

## Resolve findings {#resolve}

When you take a finding's recommended action, the finding is accepted. The upgrade assistant adds the change to the migration and applies it when you [finalize the migration](final-review.md#finalize). If you don't want to make the change, decline the finding instead.

You can reopen an accepted or declined finding if you change your mind. To update several findings at once, select them in the list.
