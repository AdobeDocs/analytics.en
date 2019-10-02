---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.dynamicAccountList

> [!NOTE] The `s.dynamicAccountList` variable is not supported in [Current AppMeasurement libraries](../../c-appmeasurement-js/appmeasure-mjs.md). It is only used in legacy AppMeasurement, such as H Code.

The `s.dynamicAccountList` variable is used to help dynamically determine a report suite to send data to. It is used in conjunction with the `dynamicAccountSelection` and `dynamicAccountMatch` variables. The rules in `dynamicAccountList` are applied if `dynamicAccountSelection` is set to `true`, and they apply to the section of the URL specified in `dynamicAccountMatch`.

## Syntax and Possible Values

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Valid input is a semicolon-separated list of name=value pairs (rules). Each list contains the following items:

* One or more report suite ID's (separated by commas)
* An equals sign
* One or more URL filters (comma-separated)

Only standard ASCII characters should be used in the string (no spaces).

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
