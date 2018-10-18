---
description: Conceptual information about query model components.
seo-description: Conceptual information about query model components.
seo-title: Query model components
solution: Analytics
title: Query model components
topic: Data workbench
uuid: 74909936-1b86-4eab-b109-c8e35a7fa270
index: y
internal: n
snippet: y
---

# Query model components

Conceptual information about query model components.

The following figure shows a dependency map whose nodes represent a query model’s metrics, derived dimensions, and filters defined in the Dimensions, Metrics, and Filters folders within the profile as well as the extended dimensions defined in the dataset that relate to them in some way.

![](assets/vis_DependencyMap_QueryModel.png)

* A yellow-green node represents a filter. 
* A purple node represents a metric. 
* A blue-green node represents a derived dimension. 
* A green node represents an extended dimension (defined in the dataset). 
* A red node represents a metric, derived dimension, or filter with a broken or circular dependency or other error.

>[!NOTE]
>
>Because the dependency map is designed to accommodate acyclic dependencies, nodes involved in circular dependencies may not display properly on the map. You can search for circular dependencies by typing “circular dependency” in the [!UICONTROL Search] text box. For more information about the [!UICONTROL Search] feature, see [Searching Within a Map](../../../c_admin_intrf/c_dataset_mgrs/c_dep_maps/t_srch_map.md#task_A1E7065A538D46C78A7D28676D880DFB).

