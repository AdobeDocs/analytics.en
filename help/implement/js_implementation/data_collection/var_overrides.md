---
description: Variable overrides let you change a variable value for a single track or track link call.
keywords: Analytics Implementation
seo-description: Variable overrides let you change a variable value for a single track or track link call.
seo-title: Variable overrides
solution: Analytics
subtopic: Variables
title: Variable overrides
topic: Developer and implementation
uuid: a49884b9-e526-4c50-ad85-807c748a2213
index: y
internal: n
snippet: y
---

# Variable overrides

Variable overrides let you change a variable value for a single track or track link call.

To override variables, create a new object, assign variable values, and pass this object as the first parameter to `s.t()`, or as the fourth parameter to `s.tl()`:

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

