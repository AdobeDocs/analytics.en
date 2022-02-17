---
title: Map tag data elements to Analytics variables
description: Assign data elements to Analytics variables so you can use them as dimensions in Analysis Workspace.
feature: Launch Implementation
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
---
# Map tag data elements to Analytics variables

Once you have a repository of tag data elements, you can assign them to Analytics dimensions.

>[!NOTE]
>Adobe Experience Platform Launch has been rebranded as a suite of data collection technologies in Experience Platform. Several terminology changes have rolled out across the product documentation as a result. Please refer to the following [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) for a consolidated reference of the terminology changes.

## Prerequisites

[Map data layer objects to data elements](layer-to-elements.md): Make sure that you understand tag data elements, and that you have several to work with.

[Create a solution design document](../prepare/solution-design.md): A solution design document is vital to staying organized. Following your solution design document simplifies the assignment of data elements to Analytics variables.

## Assign data elements to Analytics variables

Publishing a tag library after following these steps allows you to use custom dimensions in Analysis Workspace. You can set Analytics variables globally, or in individual rules.

### Set global variables

Global variables are ideal in cases where you want to set variable values on all pages where your data element exists.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Click the [!UICONTROL Extensions tab], then click [!UICONTROL Configure] under the Adobe Analytics extension.
1. Click the [!UICONTROL Global variables] accordion, which reveals the interface to assign global variables.

### Set variables in rules

Variables set in rules are ideal in cases where you don't want variables set on every page. You define the criteria in the rule. See [Rules](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) in the Adobe Experience Platform tags documentation.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Click the [!UICONTROL Rules] tab, then click on the desired rule (or create one).
1. Click the [!UICONTROL Add] button under [!UICONTROL Actions].
1. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Set Variables.
1. Click the ![Data element](assets/data-element.png) icon to the right of the desired Analytics variable. Your organization's [solution design document](../prepare/solution-design.md) dictates what Analytics variable to use.
1. Select the desired data element in the modal window. Click [!UICONTROL Select].
1. The data element name is added to the text field surrounded by `%` signs. For example, if you named your data element "Page name", you would see the string `%Page name%` when assigning a data element to a variable.

>[!TIP]
>
>You can concatenate data elements in the same variable. For example, if you have a "Hostname" data element and a "Pathname" data element, you can combine both in a single variable using `%Hostname%%Pathname%`.

## Next steps

[Page variables](../vars/page-vars/page-variables.md): Learn what page-level variables you can use in your implementation to get more out of dimensions in Analysis Workspace.

[Configuration variables](../vars/config-vars/configuration-variables.md): Learn what configuration variables you can use in your implementation to unlock more features in Adobe Analytics.
