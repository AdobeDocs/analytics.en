---
title: dynamicAccountList
description: Establish logic on how your implementation determines its report suite.
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
---
# s.dynamicAccountList

>[!IMPORTANT]
>
>Dynamic accounts are only supported using legacy JavaScript implementations (H Code). These variables are not supported in current AppMeasurement libraries or the Data Collection UI.

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
* Use the [!DNL Adobe Experience Cloud Debugger] to test the destination report suite.
