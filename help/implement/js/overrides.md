---
title: Variable overrides
description: Variable overrides let you change a variable value for a single track or track link call.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
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
