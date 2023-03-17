---
title: dynamicAccountMatch
description: The dynamicAccountMatch variable determines what value to look at in dynamic accounts.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
---
# dynamicAccountMatch

>[!IMPORTANT]
>
>Dynamic accounts are only supported using legacy JavaScript implementations (H Code). These variables are not supported in current AppMeasurement libraries or tags in Adobe Experience Platform.

The `dynamicAccountMatch` variable is the value that `dynamicAccountList` looks at and compares its values. If `dynamicAccountSelection` is not set to `true`, this variable is ignored.

If this variable is not defined, its default value is `window.location.host`.

## Syntax

```js
s.dynamicAccountMatch=[DOM object]
```

## Examples

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## Additional notes

* Pages saved to a hard drive do not have several `location` variables defined (for example, `location.host` is blank). Make sure `s_account` contains a default report suite.
* When a page is translated via a web-based translation engine, such as Google, dynamic account selection does not work as designed. For more precise tracking, populate the `s_account` variable server-side.
