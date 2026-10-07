---
title: Manage migrations in the Web SDK upgrade assistant
description: Create, view, and open migrations in the Web SDK upgrade assistant.
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
# Manage migrations

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="Migrations"
>abstract="Each migration upgrades the Adobe Analytics implementation in one tags property to the Web SDK. Open a migration to continue where you left off, or select 'New' to start one."

The **[!UICONTROL Migrations]** page is the starting point for the Web SDK upgrade assistant. It lists the migrations in your organization, including each migration's progress, status, and who created it. Use this page to create a migration or to open an existing one.

## Create a migration {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="New migration"
>abstract="Select the tags property that you want to migrate and a library in that property. The upgrade assistant takes a snapshot of the library when you create the migration. Changes made to the library after a migration snapshot are not included. Your tags property doesn't change until you finalize the migration."

<!-- markdownlint-enable MD034 -->

Before you create a migration, make sure that you meet the [prerequisites](overview.md#prerequisites).

1. On the **[!UICONTROL Migrations]** page, select **[!UICONTROL New]**.
1. Enter a name for the migration and, optionally, a description.
1. Select the tags property that you want to migrate.
1. Select a tags library. When you create the migration, the upgrade assistant takes a snapshot of your implementation as it exists in this library. Changes that you make to the library after that aren't reflected in the migration.
1. Select **[!UICONTROL Create]**.

The new migration appears in the list. Open it to start [component selection](component-selection.md).

## Open a migration {#open}

Select the name of a migration to open it. The steps of the migration appear in the left navigation. You can return to any completed step to review or change it as often as you want, but steps that you haven't reached yet aren't available.

The upgrade assistant saves your progress as you move through the steps, so you can leave a migration and return to it later. Nothing that you configure takes effect until you [finalize the migration](final-review.md#finalize). After you finalize it, the migration becomes read-only. You can still open it to see what it created, but you can't change it.

## Other migration actions {#actions}

Select a migration's row to show the actions available for it:

* **[!UICONTROL Continue]**: Opens the migration.
* **[!UICONTROL Duplicate run]**: Creates a copy of the migration.
* **[!UICONTROL Rename]**: Changes the migration's name and description.
* **[!UICONTROL Archive]**: Changes the migration's status to **[!UICONTROL Archived]**.
* **[!UICONTROL Delete migration]**: Permanently deletes the migration. You can't undo this.
