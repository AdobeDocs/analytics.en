---
title: Dynamic accounts overview
description: Learn the workflow on how to dynamically select a report suite using H Code.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
TQID: https://experienceleague.adobe.com/PCeDSQpYH3wym7oG5CYbQblnXkiOQRF4YlcHU6zYfKA
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
# Dynamic accounts overview

>[!IMPORTANT]
>
>Dynamic accounts are only supported using legacy JavaScript implementations (H Code). These variables are not supported in current AppMeasurement libraries or tags in Adobe Experience Platform.

Dynamic accounts is an implementation feature that lets you determine what report suite to use based on criteria you define. If your organization requires more than one report suite but would like to use the same implementation between your sites, dynamic accounts is a good solution.

>[!TIP]
>
>Adobe recommends sending data to a single report suite, then using virtual report suites to separate data if needed. See [Global report suite considerations](../../../prepare/global-rs.md) for more information.

3 variables are used to dynamically select a report suite.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Enable or disable dynamic account selection.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): Determines what value to observe. For example, the URL or a query string.
* [`dynamicAccountList`](dynamicaccountlist.md): Compares the values with `dynamicAccountMatch`, and if a match is found, populates the `account` variable.

If `dynamicAccountSelection = true`, the value within `dynamicAccountMatch` is compared to `dynamicAccountList`. If the values in `dynamicAccountList` match, the report suite ID is included in the `account` variable.

## Default report suite

The `account` variable can be set first, and acts as a default value in case any of the specified strings cannot be found. For example:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

If `location.hostname` was neither `dev.example.com` or `example.com`, the hit would be sent to `examplersiddefault`.

## Multi-suite tagging

Multi-suite tagging can be used with dynamic account selection. For example:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

If `location.hostname` contains `example.com`, the hit is sent to both `examplersid1` and `examplersid2`.
