---
description: Any data that you want to export must be defined as a dimension within the profile.
seo-description: Any data that you want to export must be defined as a dimension within the profile.
seo-title: Create dimensions for use with segment export
solution: Analytics
title: Create dimensions for use with segment export
topic: Data workbench
uuid: dbcb11db-a0e6-4590-a1ea-6cdd1f82c3d2
index: y
internal: n
snippet: y
---

# Create dimensions for use with segment export

Any data that you want to export must be defined as a dimension within the profile.

 If the dimension does not already exist in the profile, you must create it. You can create dimensions using any of the following methods:

* Add a dimension to the [!DNL Transformation.cfg] file. See the *Dataset Configuration Guide*. 

* Create a new [!DNL .dim] file. See [Creating and Editing Derived Dimensions](../../c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept_ECE3C3EA8CDF4FC796680173993BFF93). 

* Make selections in a visualization such as a process map or a segment and save the selections as a dimension. See [Saving Dimensions from Process Maps](../../c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task_44D9E555D4A944E6AA81993EEF703051) and [Creating Segment Dimensions](../../c-analysis-vis/c-seg/c-create-seg-dim.md#concept_70B363EDCAD14185BA8051646AD3D44E).

Exporting a field of data such as Tracking ID or Email Address (which can have lots of elements) requires that you create a denormal dimension that stores the raw strings of data.

For more information about denormal dimensions, see the *Dataset Configuration Guide*. 
