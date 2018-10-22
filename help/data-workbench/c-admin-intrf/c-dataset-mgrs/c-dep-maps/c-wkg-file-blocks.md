---
description: When you display dataset components on a dependency map, you have the option to enable the Include File Blocks display option.
seo-description: When you display dataset components on a dependency map, you have the option to enable the Include File Blocks display option.
seo-title: File blocks
solution: Analytics
title: File blocks
topic: Data workbench
uuid: c3025a5f-90e7-4831-85d5-efbafb5f53bd
index: y
internal: n
snippet: y
---

# File blocks

When you display dataset components on a dependency map, you have the option to enable the Include File Blocks display option.

 When this option is enabled, the map displays a single blue node for all of the transformations defined in one dataset configuration file and a single green node for all of the extended dimensions defined in one dataset configuration file. For example, if a [!UICONTROL log processing dataset include] file includes the definitions of three transformations, the map displays one blue node representing the three transformations. Similarly, if a [!UICONTROL transformation dataset include] file includes the definitions of two extended dimensions, the map displays one green node representing the two extended dimensions.

## Transformation blocks {#section_C442730394264A0B850792A32EAAA2DA}

Each blue node is a transformation block and has the following options:

* To view the input fields of the transformation block, right-click the node for the block and click **[!UICONTROL Inputs]**. 
* To view the output fields of the transformation block, right-click the node for the block and click **[!UICONTROL Outputs]**. 
* To edit any of the transformations in the block, right-click the node for the block and click **[!UICONTROL Edit Configuration]**. The callout that displays contains the entire configuration file in which all of the transformations are defined. You then can edit the parameters as desired. For more information about these parameters, see the *Dataset Configuration Guide*. 

* To see all of the transformations in the block, right-click the node for the transformation block and click **[!UICONTROL Show Details]**. The callout that displays contains another dependency map showing nodes for all of the transformations in the block.

## Dimension blocks {#section_0DD581AC6DFC4153BEE5300B3CFAE2A0}

Each green node is a dimension block and has the following options:

* To view the input fields or the parent dimension of the dimension block, right-click the node for the block and click **[!UICONTROL Inputs]**. 
* To view the output dimensions of the dimension block, right-click the node for the block and click **[!UICONTROL Outputs]**.

