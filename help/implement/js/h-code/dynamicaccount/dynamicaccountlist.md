---
title: dynamicAccountList
description: Establish logic on how your implementation determines its report suite.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
TQID: https://experienceleague.adobe.com/qqkQoYsBWdTDOIkNfregm4k11CoDEl3dOJ3HNCMIo3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# s.dynamicAccountList

>[!IMPORTANT]
>
>Dynamic accounts are only supported using legacy JavaScript implementations (H Code). These variables are not supported in current AppMeasurement libraries or Adobe Experience Platform Data Collection.

The `s.dynamicAccountList` variable dynamically determines the value of `s_account`. If `dynamicAccountSelection` is set to `true`, the `dynamicAccountMatch` variable is compared with `dynamicAccountList`. If a match is found, the matching report suite ID is used.

## Syntax

This variable is a string that is automatically parsed by the JavaScript file.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

Valid input is a semicolon-separated list of rsid and value pairs. Each list contains the following items:

* One or more report suite ID's (separated by commas)
* An equals sign
* One or more strings to match (separated by commas)

Only standard ASCII characters should be used in the string. Do not include spaces.

## Examples

For all the following examples, the page URL is `https://example.com/path2/?prod_id=12345`, the `dynamicAccountSelection` variable is set to `true`, and the `s_account` variable is set to `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Pitfalls, Questions, and Tips

* The rules listed in this variable are applied in a left-to-right order. If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. As a result, place more generic rules to the right of the list.
* If no rules match, the default report suite in `s_account` is used.
* If your page is saved to someone's hard drive or translated via a web-based translation engine (such as Google's translated pages), the dynamic account selection likely won't work.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.
* Use the [!DNL Adobe CX Enterprise Debugger] to test the destination report suite.
