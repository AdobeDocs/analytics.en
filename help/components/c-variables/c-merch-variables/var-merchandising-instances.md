---
description: Describes how instances are counted on merchandising variables.
keywords: Analytics Implementation
solution: Analytics
title: Instances on merchandising variables
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
---

# Instances on merchandising variables

Describes how instances are counted on merchandising variables.

 Instances are not currently supported for merchandising variables. If you notice instances in a report containing a merchandising variable, it indicates that the eVar is being set in some locations outside of the products string and should not be considered as a true count of instances for the selected merchandising variable.

If you are using Conversion Variable Syntax, an instance is counted each time the variable is set. However, the instance is attributed to "None" unless the following occurs each time the variable is set:

* A binding event is set.
* The products variable is set.
* The merchandising eVar has a value.

For example, the following instance of eVar1 is allocated to "Outdoors:Ski Goggles":

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

However, in the next example, the instance of eVar1 is allocated to "None" since all conditions are not met when the eVar is set (there is no binding event and the products variable is not set):

Page 1 of the visit:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Page 2 of the visit:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Allocation to "None" occurs if you set a value for an eVar on a page where no binding event occurs, or if you set the eVar value in the products string without a binding event.

> [!NOTE] The current functionality for counting instances on merchandising variables is being reviewed and is scheduled to change in an upcoming release.

