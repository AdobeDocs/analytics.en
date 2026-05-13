---
description: Virtual report suites can be curated to include and exclude components.in Analysis Workspace.
title: Virtual report suite component curation
feature: VRS
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
TQID: https://experienceleague.adobe.com/j86dD5Yzd6GIoQOzhHsU8YbShQiODtbU8aCdM3UxRMg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
    internal-label: Workspace projects
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Virtual report suite component curation

Virtual report suites can be curated to include and exclude components.in Analysis Workspace.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Component curation](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/virtual-report-suites/component-curation-in-virtual-report-suites){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Changes were made to which components administrators and non-administrators can see in curated Workspace projects and curated virtual reports suites. Previously, anyone could see non-curated components by clicking **[!UICONTROL Show all Components]**. The [updated curation experience](/help/analyze/analysis-workspace/curate-share/curate.md) allows for more fine-grained control over which components are visible.

To enable component curation,

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]** > **[!UICONTROL Create new virtual report suite]**.
1. After defining the **[!UICONTROL Settings]**, click the **[!UICONTROL Components]** tab.

1. Select the checkbox **[!UICONTROL Enable Customization of Virtual report suite components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >If component customization is enabled, the virtual report suite is accessible **only in Analysis Workspace** and is not accessible in the following:
   >
   >* [!UICONTROL Data Warehouse] 
   >* [!UICONTROL Report Builder] 
   >* [!UICONTROL Activity Map]
   >* Analytics Reporting API

   Once checked, you can add the components you'd like to be included in the virtual report suite by dragging the applicable components from the "excluded components" column to the "included components" column. The components that can be included and excluded are:

    * Dimensions 
    * Metrics 
    * Segments 
    * Date Ranges

   >[!NOTE]
   >
   >There is no need to *share* curated components (segments, calculated metrics, date ranges). They will always be visible in Analysis Workspace if they are curated for the virtual report suite, even if they are not shared.

1. Additionally, you can filter or search the components and add the entire filtered selection to the included column by clicking **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## Rename Components {#section_0F7CD9F684FE4765BC00A2AFED56550E}

You can change the display names of included components specific to the virtual report suite. For example, if you want to include Page Name in the virtual report suite, but want to rename it to a more mobile friendly context, you can change it to App Screens. The new name is displayed in Analysis Workspace whenever this virtual report suite is used.

![](assets/vrs-rename-component.png)

In Analysis Workspace, click the information icon for any included component to reveal the original name of the renamed component:

![](assets/vrs-aw-renamed.png)

## Component Groups {#section_483BEC76F49E46ADAAA03F0A12E48426}

Use component groups to make bulk component additions to your virtual report suite. For example, if you'd like to import a default set of components specific to mobile app analysis, select the mobile app group. A corresponding set of dimensions and metrics (already renamed) are automatically added to the virtual report suite Included list.

![](assets/vrs-comp-grp.png)

## Workspace Behavior {#section_6C32F8B642804C0097FCB14E21028D4A}

For more information on curation in Analysis Workspace, see [Curate and Share a Project](/help/analyze/analysis-workspace/curate-share/curate.md).
