---
description: With the Calculated Metric builder, anyone can create a participation metric.
seo-description: With the Calculated Metric builder, anyone can create a participation metric.
seo-title: Participation Metric
title: Participation Metric
uuid: 08a8e1fd-a2e9-4242-8a79-95913e4ef3e8
index: y
internal: n
snippet: y
translate: y
---

# Participation Metric


>[!NOTE]
>
>You used to have to do this via the Admin Console. You can still enable participation metrics in the Admin Console, but only for custom events 1 - 100.

Here is a simple use cases: You are a content owner and you want to see which pages contributed to (participated in) visits that contained an email sign-up. Here’s how: 

1. Create a new metric in the Calculated Metric Builder.
1. Drag the success event "Email sign-up" into the Definition canvas.
1. Change the [ allocation](m_metric_type_alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) of that event to Visit Participation. The definition should look similar to this: ![](graphics/participation.png) 

1. Save the metric.
1. Share it with the people who need it in your company.
