---
title: Entries
description: An instance of the first value in a visit.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
---
# Entries

*This help page describes how entries work as a metric. For information on how entries work as a dimension, see [Entry dimensions](../dimensions/entry-dimensions.md).*

The 'Entries' metric shows the number of times a given dimension item is captured as the first value in a visit. This metric is helpful when you want to understand more about the first impressions visitors have on your site. Seeing the first values of a dimension can help you understand and optimize the experience a new visitor gets.

## How this metric is calculated

For a given dimension, record the first dimension item seen in a visit as an entry. Only one entry exists per dimension per visit. It is not necessarily the first hit of the visit if the dimension is not initially set. It is a visit-based metric; once it ties to a dimension item, it persists for the rest of the visit.

>[!TIP]
>
>If you view this metric against a dimension not always set in every visit, you can hide the 'Unspecified' dimension item in Analysis Workspace. Click the filter icon, then uncheck [!UICONTROL Include unspecified (None)].
