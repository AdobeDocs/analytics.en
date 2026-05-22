---
description: Administrators are responsible for monitoring Data Dictionary health. This includes whether components are gathering data, are approved, contain descriptions, and are free from duplicates.
title: Monitor Data Dictionary health
feature: Components
role: Admin
exl-id: 82176931-2bd9-4f4e-9ca7-4214d44151a8
TQID: https://experienceleague.adobe.com/q-wAiW4oUc9kH-ywKVLfNKtXHdEfnIr01GXSK-g0YqY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
    internal-label: Data Dictionary
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Monitor Data Dictionary health {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_share_primary"
>title="Share primary component"
>abstract="When this option is selected, the primary component is shared with everyone who has access to the duplicate components (both the owners and anyone the components are shared with). Those users can then select the primary component from the component list for future projects. However, they are not able to edit the component, even if they were the owner of a duplicate component that was consolidated. <br/>This option is available only when the primary component is a segment, calculated metric, or a date range. Metrics and dimensions are always available to all users.  
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_delete_duplicates"
>title="Delete replaced duplicates"
>abstract="When this option is selected, consolidated duplicates are no longer available for use. Deselect this option if you want duplicates to continue to be available."

<!-- markdownlint-enable MD034 -->

Analytics administrators are responsible for maintaining a healthy Data Dictionary. 

## Characteristics of a healthy Data Dictionary

A healthy Data Dictionary is one where all components:

* Are being used and are gathering data

* Contain helpful descriptions so users know how best to use them

* Are free from unnecessary duplicates

* Are approved by the administrator

## Check the health of your Data Dictionary

To identify health issues in your Data Dictionary:

1. Open an Analysis Workspace project.

1. Select the Data Dictionary icon on the left side of Analysis Workspace. (Alternate ways of accessing the Data Dictionary are described in "Access the Data Dictionary" in [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   The Data Dictionary window displays.

   ![Data Dictionary admin view](assets/data-dictionary-admin.png)

1. Ensure that the correct Report Suite is selected in the drop-down menu.

1. On the [!UICONTROL **Dictionary health**] tab, select [!UICONTROL **View**] next to any of the following options:

   * [!UICONTROL **components are missing descriptions**]

   * [!UICONTROL **components have duplicates**]

   * [!UICONTROL **components have no data connected**]

   Depending on what you select, the appropriate filter is applied to the Data Dictionary, and only the relevant components are shown. 

1. Edit any of the components to improve the health of the Data Dictionary. For information about how to edit a component in the Data Dictionary, see [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).
