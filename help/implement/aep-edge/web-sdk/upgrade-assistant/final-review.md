---
title: Final review in the Web SDK upgrade assistant
description: Review and finalize a Web SDK migration, then publish the resulting tags library to production.
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
# Final review

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="Final review"
>abstract="Select the Experience Platform sandbox to use, then review everything that this migration creates or changes. Nothing changes until you finalize the migration. When you finalize it, the upgrade assistant creates everything at once, adds the tags changes to a new library, and makes this migration read-only. You then publish that library to production yourself."

<!-- markdownlint-enable MD034 -->

Final review is the last step of a migration. It shows everything that the migration creates or changes in Experience Platform and in your tags property.

## Review what the migration creates {#review}

First, select the Experience Platform sandbox that the migration creates its resources in. You can't finalize the migration until you select a sandbox.

The upgrade assistant then lists everything that finalizing the migration creates or changes:

* **[!UICONTROL XDM]**: A new schema named after your XDM mapping, along with the custom field groups that it needs. Standard field groups already exist, so the schema uses them as they are. This section appears only if you chose to create a new schema in [XDM mapping](xdm-mapping.md#schema).
* **[!UICONTROL Datasets]**: Two datasets, one for development and one for production. Each is named after the migration, such as `My migration - Development`.
* **[!UICONTROL Datastreams]**: Two datastreams, one for development and one for production, named the same way as the datasets.
* **[!UICONTROL Adobe Tags]**: A new library named after the migration, such as `Library - "My migration"`. The library contains the rules and data elements that the migration changes, along with the extension configuration that the Web SDK actions need.

## Finalize the migration {#finalize}

Until you finalize the migration, the upgrade assistant doesn't change your tags property or create anything in Experience Platform.

>[!IMPORTANT]
>
>After you finalize a migration, it becomes read-only. You can still open it from the **[!UICONTROL Migrations]** page to see what it created, but you can't change it or finalize it again. Because the new library is still in development, you can edit or remove the tags changes in the tags UI before you publish the library.

1. Select **[!UICONTROL Create artifacts]**.
1. In the **[!UICONTROL Verify these recommendations]** dialog, select **[!UICONTROL Continue]**.
1. In the **[!UICONTROL Finalize this migration?]** dialog, select **[!UICONTROL Finalize]**.

The upgrade assistant creates everything at once and shows its progress. It adds the tags changes to the new library, but it doesn't publish the library.

## Publish your changes {#publish}

After you finalize the migration, move the new library through the tags publishing flow:

1. Build and test the library in your development environment to make sure that your Web SDK implementation sends the data that you expect.
1. Submit the library for approval and test it in your staging environment.
1. Approve the library and publish it to production.

See [Publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow) in the Tags user guide.
