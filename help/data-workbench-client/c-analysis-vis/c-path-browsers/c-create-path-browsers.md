---
description: You can create a path browser from a graph, table, or process map.
seo-description: You can create a path browser from a graph, table, or process map.
seo-title: Creating path browsers
solution: Analytics
title: Creating path browsers
topic: Data workbench
uuid: 1a165b2f-b814-4492-a772-382843a4d7ec
index: y
internal: n
snippet: y
---

# Creating path browsers

You can create a path browser from a graph, table, or process map.

 **To create a path browser from a graph or table**

1. Add a path browser to your workspace. The visualization is blank except for the label (Sequence of...) in the top left corner. 
1. Open a graph or table showing the dimension whose elements you want displayed on the path browser. For example, if you are working with website data, open a page graph or table and identify the page that you want to set as the root. 
1. Press Ctrl+Alt and drag the desired element to the path browser. The label in the top left corner of the path browser changes to reflect the base dimension whose element you drag to the path browser.

>[!NOTE]
>
>Dragging an element to a path browser may change the base dimension associated with the path browser, but it does not change the level dimension, group dimension, or metric. Therefore, you must exercise caution in choosing a base dimension that makes sense when used with the path browser’s level dimension, group dimension, and metric. To change the level dimension, group dimension, or metric, you must edit the path browser’s [!DNL *.vw] file in a text editor such as Notepad. See [Configuring Path Browsers](../../../data-workbench-client/c-intf-anlys-ftrs/t-config-path-brwsr.md#task_BBB3DDAA140A414F984B697C2B8202A3).

**To create a path browser from a process map**

>[!NOTE]
>
>A path browser created from a process map displays only the elements shown on the process map. Other elements of the base dimension are not displayed.

1. Create a process map. See [Creating Process Maps](../../../data-workbench-client/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept_DAF5B14DAE7A442191611B1B9C1122BF). 
1. Drag the desired element from the process map to the path browser. The element becomes the root of the path browser.

>[!NOTE]
>
>When you create a path browser from a process map, the path browser ignores the elements of the level dimension with no associated base dimension elements. When you drag a node from a process map onto a path browser, the path browser’s base dimension (named Map) is defined by the process map, and its elements are limited to the elements on the process map. As a result, some elements of the path browser’s level dimension do not have associated base dimension elements and are not represented in the path browser.

