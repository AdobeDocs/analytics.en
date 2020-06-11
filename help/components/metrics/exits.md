---
title: Exits
description: An instance of the last value in a visit.
---

# Exits

*This help page describes how exits work as a metric. For information on how exits work as a dimension, see [Exit dimensions](../dimensions/exit-dimensions.md).*

The 'Exits' metric shows the number of times a given dimension value is captured as the last value in a visit. This metric is helpful when you want to understand more about the last thing visitors see before leaving your site. Seeing the last values of a dimension can help you understand and optimize the experience a visitor gets before they leave.

## How this metric is calculated

After a [visit](visits.md) concludes, record the most recent dimension value as an exit. Only one exit exists per dimension per visit. It is not necessarily the last hit of the visit if the dimension was set in previous hits. It is a visit-based metric; it retroactively applies to all hits in the visit.

>[!TIP] If you view this metric against a dimension not always set in every visit, you can hide the 'Unspecified' dimension value in Analysis Workspace. Click the filter icon, then uncheck [!UICONTROL Include unspecified (None)].
