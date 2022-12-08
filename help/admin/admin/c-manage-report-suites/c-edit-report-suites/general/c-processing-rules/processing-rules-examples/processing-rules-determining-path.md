---
description: You can copy the value of an eVar to a prop to enable pathing.
subtopic: Processing rules
title: Determine a path by copying an eVar value to a prop
feature: Admin Tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
---
# Determine a path by copying an eVar value to a prop

You can copy the value of an eVar to a prop to enable pathing.

When setting values, the variable on the left receives the value (even if it is empty) from the variable on the right.

|  Rule Set  | Value  |
|---|---|
|  Condition  | None (always execute)  |
|  Action  | Overwrite Value of Prop1 with eVar1  |

You can modify this rule to set the value of Prop1 only if it does not already contain a value, similar to the following: 

|  Rule Set  | Value  |
|---|---|
|  Condition  | If Prop1 Is Not Set  |
|  Action  | Overwrite Value of Prop1 with eVar1  |

For example:

![](assets/overwrite-empty-prop.png)
