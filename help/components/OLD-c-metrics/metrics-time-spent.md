---
description: Adobe Analytics offers various Time Spent metrics and dimensions. Find out what they are and how they are calculated.
title: Time Spent
topic: Metrics
---







## Examples of [!UICONTROL Time Spent] calculations

Assume the following set of server calls are for a single visitor within a single visit:

|Visit hit#|1|2|3|4|5|6|7|
|---|---|---|---|---|---|---|---|
|**Visit elapsed time (in sec)**|0|30|80|180|190|230|290|
|**Seconds spent**|30|50|100|10|40|60|-|
|**Hit type**|Page|Link|Page|Page|Page|Page|Page|
|**Page Name**|Home|-|Product|Home|Home (reload)|Cart|Order confirmation|
|||||||||
|**prop1**|A (set)|A (spread forward)|not set|B (set)|B (set)|A(set)|C (set)|
|**prop1 seconds spent**|30|50|-|10|40|60|-|
|||||||||
|**eVar1**|Red (set)|Red (persisted)|(expired)|Blue (set)|Blue (set)|Blue (persisted)|Red (set)|
|**eVar1 seconds spent**|30|50|-|10|40|60|-|

Based on the table above, time spent metrics are calculated as follows:

|prop1|Total seconds spent|Time spent per visit|Time spent per visitor|Count of sequences|Average time spent on site|
|---|---|---|---|---|---|
|A|30+50+60=140|140/1=140|140/1=140|2|140/2=70|
|B|10+40=50|50/1=50|50/1=50|1|50/1=50|
|C|0|0|0|0|0|
|Unattributed time|100|-|-|-|-|

|eVar1|Total seconds spent|Time spent per visit|Time spent per visitor|Count of sequences|Average time spent on site|
|---|---|---|---|---|---|
|Red|30+50=80|80/1=80|80/1=80|1|80/1=80|
|Blue|10+40+60=110|110/1=110|110/1=110|1|110/1=110|
|Unattributed time|100|-|-|-|-|

Time spent per visit (granular): 290
Time spent on page (granular): 10, 30, 40, 50, 60, 100

Some additional notes in support of the example:

* All time spent calculations are based on the visit elapsed time which starts at zero on the first hit of the visit. 

* “Seconds spent” is the difference between the timestamp of the current hit and the timestamp of the next hit. As a result, the last hit of the visit (and bounces) have no time spent.

* A “sequence” is a consecutive set of hits where a given variable contains the same value (whether by being set, spread forward, or persisted). For example, prop1 “A” has two sequences: hits 1 & 2 and hit 6. Values on the last hit of the visit do not start a new sequence because the last hit has no time spent. Average time spent on site uses sequences in the denominator.

    * For the purposes of time spent only, props are “spread forward” from page hits to subsequent link hits as shown above for prop1 on hit 2. This allows the value that was set for prop1 on hit 1 (“A”) to accumulate time spent on hit 2.
    
    * eVars accumulate time spent on any hit where the eVar is set or persisted. eVar persistence is defined by the eVar settings in Analytics > Admin.
