---
description: Labeling report suite data means that you assign identity, sensitivity, and data governance labels to each variable in a given report suite.
title: Privacy labeling overview
feature: Data Governance
role: Admin
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
TQID: https://experienceleague.adobe.com/xEs37qiYjTVJWRDKa7HwJqfTtyBYKstA6ehq1-0qKt0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
  - id: b99602d0-836e-4dbb-979f-c0dec53f883c
    internal-label: Privacy
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Privacy labeling overview

Labeling report suite data means that you assign identity, sensitivity, and data governance labels to each variable in a given report suite. Make sure that you first familiarize yourself with the [labels and their definitions](/help/admin/tools/privacy-labeling/labels.md).

>[!NOTE]
>
>Remember that Labeling needs to be reviewed each time a new report suite is created or when a new variable is enabled within an existing report suite. You may also need to review the labeling when new solution integrations are enabled, as they can expose new variables that may require labeling. A re-implementation of your mobile apps or websites may change the way that existing variables are used, which may also necessitate updates to labels.

## Assign or edit report suite privacy labels {#assign-edit}

**Example**: You, as the Data Controller, plan to collect email addresses and cookie IDs from Data Subjects to process their Data Privacy requests. These cookie IDs are stored in a report suite in Adobe Analytics.

1. In Adobe Analytics, navigate to **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Data governance]**.

   ![Privacy labeling](assets/privacy_rs_settings.png)

1. Select a report suite from the **[!UICONTROL Report Suites]** selector at the top. 

1. In the filter section on the left, select which groups of variables you want to label. You can label only one group of variables at a time.

   * **Standard Components** - Standard components are out-of-the-box Analytics dimensions and metrics that are collected by default within an Analytics implementation.
   * **Conversion Variables** - The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports. An eVar can be visit based and function similarly to cookies. Values passed into eVar variables follow the user for a predetermined period of time.
   * **List Variables** - List variables are custom variables that you can use however you would like. They work similarly to eVars, except they can contain multiple values in the same hit. List variables do not have a character limit.
   * **Traffic Variables** - Custom Insight Traffic Variables (or props) enable you to correlate custom data with specific traffic-related events. The prop variables are embedded in the implementation code on each page of your website.
   * **Success Events** - Success events (also known as conversion events or custom events) are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.
   * **Classifications** - Classification breakdowns are used to map Analytics reporting data to related properties. Classifications can be used for a variety of purposes, but are most commonly used for classifying campaign tracking codes (both internal and external) and product IDs.

1. Select a variable by clicking its checkbox, then click **[!UICONTROL Edit Privacy Labels]** on the blue bar that appears at the bottom of the screen.

   ![Edit](assets/edit-label.png)

   This screen shows currently applied labels and allows you to apply additional labels. You may not be able to apply or modify all labels, depending on the component.

   ![Applied labels](assets/edit-labels2.png)

1. Click **[!UICONTROL Apply]** once you have completed all labeling.

