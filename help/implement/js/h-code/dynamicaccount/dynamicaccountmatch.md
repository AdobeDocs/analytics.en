---
title: dynamicAccountMatch
description: The dynamicAccountMatch variable determines what value to look at in dynamic accounts.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
TQID: https://experienceleague.adobe.com/Ag4YQOjHPMRsktGSbzpErM55lVCydDHXfNiS4HJofIU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
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
