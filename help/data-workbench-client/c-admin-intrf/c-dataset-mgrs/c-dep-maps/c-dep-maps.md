---
description: Dependency maps enable you to visualize and manage the configuration of components of your profile.
seo-description: Dependency maps enable you to visualize and manage the configuration of components of your profile.
seo-title: Dependency maps
solution: Analytics
title: Dependency maps
topic: Data workbench
uuid: e0e5ac80-9764-4979-b100-2e03c359d866
index: y
internal: n
snippet: y
---

# Dependency maps

Dependency maps enable you to visualize and manage the configuration of components of your profile.

* **Dataset components:** Log sources, filters, fields, transformations, and extended dimensions defined in your dataset’s [!DNL Log Processing.cfg], [!DNL Transformation.cfg], and dataset include files.

  For more information about defining log sources, fields, transformations, and extended dimensions in dataset configuration files, see the *Dataset Configuration Guide*. 

* **Query model components:** Metrics, dimensions, and filters defined in the Dimensions, Metrics, and Filters folders 
* **Workspaces and visualizations:** Workspaces, reports, menu options, and globe layers

Profile components are represented by colored dots (nodes) in the map. The lines connecting the nodes depict dependencies, that is, how the components relate to one another. A line between two nodes means that an output of the node on the left is an input of the node on the right, that is, the right node depends on the left node. 
