---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.dynamicAccountList

[!DNL AppMeasurement] for JavaScript can dynamically select a report suite to which it sends data. The  variable contains the rules used to determine the destination report suite.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | ""  |

This variable is used in conjunction with the *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in `s_account` is used. The rules listed in this variable are applied in a left-to-right order. If the page URL matches more than one rule, the left-most rule is used to determine the report suite. As a result, your more generic rules should be moved to the right of the list.

In the following examples, the page URL is `www.mycompany.com/path1/?prod_id=12345` and `dynamicAccountSelection` is set to *true* and `s_account` is set to `mysuitecom.`

|  DynamicAccountList Value  | DynamicAccountMatch Value  | Report Suite to Receive Data  |
|---|---|---|
|  `mysuite2=www2.mycompany.com;mysuite1=mycompany.com`  | window.location.host  | mysuite1  |
|  "mysuite1=path4,path1;mysuite2=path2"  | window.location.pathname  | mysuite1, mysuite2  |
|  "mysuite1=path5"  | window.location.pathname  | mysuitecom, mysuite1  |
|  "myprodsuite=prod_id"  | window.location.search?window.location.search:"?")  | myprodsuite  |

## Syntax and Possible Values

The `dynamicAccountList` variable is a semicolon-separated list of name=value pairs (rules). Each piece of the list should contain the following items:

* one or more report suite ID (separated by commas)
* an equals sign
* one or more URL filters (comma-separated)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

Only standard ASCII characters should be used in the string (no spaces).

## Examples

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). 
* If the page URL matches multiple rules, the furthest rule on the left is used. 
* If no rules match, the default report suite is used. 
* If your page is saved to someone's hard drive or translated via a web-based translation engine (such as Google's translated pages), the dynamic account selection probably won't work. For more precise tracking, populate the `s_account` variable server-side. 
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain. 
* Use the [!DNL DigitalPulse Debugger] when trying to identify the destination report suite. The `dynamicAccountSelection` variable always overrides the value of `s_account`.
