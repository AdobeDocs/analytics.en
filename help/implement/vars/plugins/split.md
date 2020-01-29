---
title: split
description: Utility function that splits a string
---

# split

The `split` plug-in is a utility used by other plug-ins.

```js
// Utility Function: split v1.5 - split a string (JS 1.0 compatible)
s.split= function (l,d){var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x++]=l.substring(0,i);l=l.substring(i+d.length);}return a};
```
