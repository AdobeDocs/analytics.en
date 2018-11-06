---
description: The import and export file includes six columns for each numeric 2 classification.
seo-description: The import and export file includes six columns for each numeric 2 classification.
seo-title: Import numeric 2 classifications
solution: Analytics
subtopic: Classifications
title: Import numeric 2 classifications
topic: Admin tools
uuid: 82a3034c-e002-4991-900f-22dd45d54910
index: y
internal: n
snippet: y
---

# Import numeric 2 classifications

The import and export file includes six columns for each numeric 2 classification.

The following definitions assume that your numeric 2 classification name is MyCost.

**~MyCost:** A descriptive name for the row.

**~MyCost^~id~:** The ID for editing an existing row. When you add a new row, this should be blank. An ID is automatically assigned when you export from the Classification Manager.

**~MyCost^~value~: **The value for the row. If the rate column is fixed, then this is a flat value distributed over the whole period. If the rate column is an event, then this is the multiplier for that event. This entry should not contain commas.

**~MyCost^~period~:** The period of time to which this row corresponds. This must include a beginning and ending date, separated by a dash. The dash must be enclosed in spaces. The definition should be formatted as follows:

YYYY/MM/DD - YYYY/MM/DD

**~MyCost^~rate~:** The event to multiply by the [!UICONTROL Value] column. Valid values are:

* fixed - used to indicate that value is a flat value to be spread over the period. 
* revenue 
* order 
* unit 
* scopen 
* scviews 
* instance 
* click 
* checkout 
* scadd 
* scremove 
* event 1 
* event 2 
* etc

**~MyCost^~hinge~:** The event to use to distribute the value during a breakdown. This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none]. 
