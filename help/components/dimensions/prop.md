---
title: Prop
description: A custom dimension you can use in reporting.
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
---
# Prop

*This help page describes how props work as a dimension. For information on how to implement props, see [props](/help/implement/vars/page-vars/prop.md) in the Implement user guide.*

Props are custom variables that you can use however you'd like. They do not persist beyond the hit that they are set.

>[!TIP]
>
>Adobe recommends using [eVars](evar.md) in most cases. In previous versions of Adobe Analytics, props and eVars had advantages and disadvantages to each other. However, Adobe has improved eVars to where they fulfill almost all use cases for props.

If you have a [solution design document](/help/implement/prepare/solution-design.md), you can allocate these custom dimensions to values specific to your organization. The number of available props depends on your contract with Adobe. Up to 75 props are available if your contract with Adobe supports it.

## Populate props with data

Each prop collects data from the [`c1` - `c75` query string](/help/implement/validate/query-parameters.md) in image requests. For example, the `c1` query string parameter collects data for prop1, while the `c68` query string parameter collects data for prop68.

AppMeasurement, which compiles JavaScript variables into an image request for data collection, uses the variables `prop1` - `prop75`. See [prop](/help/implement/vars/page-vars/prop.md) in the Implement user guide for implementation guidelines.

## Dimension items

Since props contain custom strings in your implementation, your organization determines what the dimension items are for each prop. Make sure you record the purpose of each prop and typical dimension items in a [solution design document](/help/implement/prepare/solution-design.md).

## Case sensitivity

Props, by default, are not case-sensitive. If you send the same value in different cases (for example, `"DOG"` and `"Dog"`), Analysis Workspace groups them together into the same dimension item. The case of the first value seen at the beginning of the reporting month is used. Data Warehouse shows the first value encountered during the request period.

You can make any prop case-sensitive. You can also disable case-sensitivity for any prop once it is enabled. Contact Adobe Customer Care with the report suite ID and the desired variables(s) to toggle case sensitivity. 

>[!IMPORTANT]
>
>Toggling case sensitivity can cliff dimension items, causes unexpected results with segments, and causes issues with filters. Adobe strongly recommends toggling this setting between two major time periods, such as the beginning of a month or year.

## Value of props over eVars

Adobe recommends using eVars in most cases. Exceptions to this statement are as follows:

* You can use props in real-time reports. eVars take at least 30 minutes to appear in reporting.
* Props have the ability to become list props, which accept multiple values in the same hit. List vars are a separate variable, and there are only three list variables available.
* When you enable pathing on a prop, [Entry](entry-dimensions.md) and [Exit](exit-dimensions.md) dimensions immediately become available. If you want entry and exit dimensions for eVars, you can manually create a segment.

See [eVar](evar.md) for more comparisons between props and eVars.
