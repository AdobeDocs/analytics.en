---
description: Entries represents the number of times a given value is captured as the first value in a visit. Entries can occur only once per visit. However, it is not necessarily the first hit if the variable is not defined.
title: Entries
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
---

# Entries

"Entries" represents the number of times a given value is captured as the first value in a visit. Entries can occur only once per visit. However, it is not necessarily the first hit if the variable is not defined.

In Analysis Workspace, as of March 2020, we have changed how the "None" value interacts with Entries/Exits.  Because you can now turn "Nones" on and off in Analysis Workspace, we apply the "None" after the entry or exit, whereas (for evars) it used to be applied before.  For example, assume the first hit of a visit has no value for, say, eVar21, but the second hit does. In Reports & Analytics it will show up as "Unspecified" for the Entry, but in Analysis Workspace it will show up as the value on the second hit.

Entry pages have a visit breakdown scope, meaning they persist across all hits for a visit. See [Breakdown and segmentation containers](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) for more information.
