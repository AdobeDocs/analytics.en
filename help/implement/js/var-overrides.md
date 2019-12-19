---
title: Variable overrides
description: Variable overrides let you change a variable value for a single track or track link call.
---

# Variable overrides

Variable overrides let you change Analytics values for a single hit without affecting existing variables on the page.

## Workflow

1. Create a new JavaScript object. The object name can be anything you want.

   ```js
   var override = new Object();
   ```

2. Assign valid Analytics properties to this object:

   ```js
   override.eVar1 = "New value";
   override.events = "event2";
   ```

3. Use the object as an argument within the appropriate tracking call:

   ```js
   // Use the override object in a standard page view call
   s.t(override);

   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',override);
   ```

When a tracking call receives an object in the overrides parameter, all valid values in the override object overwrite values in the standard Analytics object. Variables already defined in your existing Analytics object are not affected.
