---
title: Variable overrides
description: Variable overrides let you change a variable value for a single track or track link call.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
TQID: 'https://experienceleague.adobe.com/IVA-JMaZPrKpF1NhhL6o3uiCQOOCtZerk78aQTqJAyc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Variable overrides

Variable overrides let you change Analytics values for a single hit without affecting existing variables on the page.

## Workflow

1. Create a new JavaScript object. The object name can be anything you want.

   ```js
   var y = new Object();
   ```

2. Assign valid Analytics properties to this object:

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. Use the object as an argument within the appropriate tracking call:

   ```js
   // Use the override object in a standard page view call
   s.t(y);

   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

When a tracking call receives an object in the overrides parameter, all valid values in the override object overwrite values in the standard Analytics object. Variables already defined in your existing Analytics object are not affected.
