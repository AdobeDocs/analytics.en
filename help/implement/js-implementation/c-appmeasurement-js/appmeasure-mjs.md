---
description: AppMeasurement for JavaScript is a new library that provides the same core functionality of s_code.js, but is lighter and faster for use on both mobile and desktop sites.
keywords: appmeasurement;Analytics Implementation;javascript;appmeasurement for javascript;initialization;retrieve appmeasurement instance;clear vars;clearvars;appmeasurement utilities;appmeasurement instance;appmeasurement benefits
seo-description: AppMeasurement for JavaScript is a new library that provides the same core functionality of s_code.js, but is lighter and faster for use on both mobile and desktop sites.
seo-title: About AppMeasurement for JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: About AppMeasurement for JavaScript
topic: Developer and implementation
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
---

# About AppMeasurement for JavaScript

[!DNL AppMeasurement] for JavaScript is a new library that provides the same core functionality of s_code.js, but is lighter and faster for use on both mobile and desktop sites.

## Things to know before you migrate {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* Some plug-ins are no longer supported. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A). 
* The library does not support dynamic account selection ( [dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md). 

* The library and page code can be deployed inside the `<head>` tag. 
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. The Survey module is not supported. 
* Your existing page code is compatible with the new version. 
* The library provides native utilities to get query parameters, read and write cookies, and perform advanced link tracking.

## Frequently Asked Questions {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## Initialization process {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

When `s_gi` is called, if an [!DNL AppMeasurement] instance does not exist for the specified `s_account`, a new instance is created. Otherwise the existing instance is returned. This helps avoid creating duplicate objects for the same account.

## Retrieve an [!DNL AppMeasurement] instance {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## Utilities {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D) 
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2) 
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## Clear Vars {#section_597C411E7EDB42BC9A6A0508C9D57147}

A new `clearVars` method is available to clear the following values from the instance object:

* `props` 
* `eVars` 
* `hier` 
* `list` 
* `events` 
* `eventList` 
* `products` 
* `productsList` 
* `channel` 
* `purchaseID` 
* `transactionID` 
* `state` 
* `zip` 
* `campaign`

For example:

```js
s.clearVars()
```

## Benefits {#section_091E5A28E89E438E8A54A95F55165743}

* 3-7x faster than H.25 code. 
* Only 21k uncompressed and 8k gzipped (H.25 code is 33k uncompressed and 13k gzipped). 
* Native support for several common plugins (). 
* Small and fast enough to be used with mobile sites, and robust enough to be used on the full desktop web, allowing you to leverage a single library across all web environments.

