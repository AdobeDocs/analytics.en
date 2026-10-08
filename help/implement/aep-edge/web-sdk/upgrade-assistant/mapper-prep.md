---
title: Mapper preparation in the Web SDK upgrade assistant
description: Review the Analytics variables in your report suites and choose which ones to carry forward into XDM mapping.
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
# Mapper preparation

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep"
>title="Mapper preparation"
>abstract="Review the Analytics variables that your tags property sends to each report suite. Variables that you select here carry forward to XDM mapping. Use the tabs to check for recent data, find duplicate variables, and compare settings across report suites."

<!-- markdownlint-enable MD034 -->

The upgrade assistant identifies the report suites that your tags property sends data to, then compares the Analytics variables in your implementation against each report suite's configuration and recent data. Use this step to decide which variables carry forward to [XDM mapping](xdm-mapping.md).

The upgrade assistant uses your report suites to understand which variables your implementation sets and how they're configured. Activity data covers the last 90 days.

## Variable activity {#variable-activity}

The **[!UICONTROL Variable activity]** tab lists the Analytics variables for the report suite that you chose to map in [Variable analysis](#variable-analysis), and shows whether each one has collected data in the last 90 days.

Variables that you select carry forward to XDM mapping. Consider clearing variables that no longer collect data or that you don't need in your Web SDK implementation. A variable with no recent activity might still be in use, for example if it's seasonal or has low traffic, so confirm that you don't need it before you clear it.

For each list variable and list prop that you carry forward, enter the delimiter that separates its values. The upgrade assistant can't get delimiters from Adobe Analytics, and you can't continue until each one has a delimiter.

## Variable analysis {#variable-analysis}

If your tags property sends data to more than one report suite, first choose the report suite to map. The **[!UICONTROL Variable analysis]** tab then flags variables that might need a decision before you map them:

* Variables that appear to collect the same data. Confirm that they capture the same information, then decide whether to merge them into a single variable or keep them separate.
* Variables that haven't collected data recently.
* Variables whose values are all "Unspecified".

## Compare report suites {#compare}

If your tags property sends data to more than one report suite, the **[!UICONTROL Compare report suites]** tab compares each variable's settings across up to three of those report suites. Use it to find variables that are configured differently between report suites before you map them to a schema.

## Update report suite data {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep_refresh"
>title="Refresh report suite data"
>abstract="Checks the report suites linked to this tags property again, including their variable settings and recent data, then reruns the variable analysis. If the upgrade assistant hasn't found any report suites yet, it looks for them in the tags property first. Your selections and decisions are kept."

<!-- markdownlint-enable MD034 -->

You can change which report suites the upgrade assistant analyzes during this step. If your report suite configuration changes while a migration is in progress, select **[!UICONTROL Refresh report suite data]** to rerun the analysis. The upgrade assistant keeps your existing selections and decisions.

When you're done, select **[!UICONTROL Save and continue]** to go to [XDM mapping](xdm-mapping.md).
