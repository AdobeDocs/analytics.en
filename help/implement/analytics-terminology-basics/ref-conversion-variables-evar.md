---
description: The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports.
keywords: Analytics Implementation;eVar;conversion variable;eVar value;conversion;success event
seo-description: The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports.
seo-title: Conversion variables (eVars)
solution: Analytics
title: Conversion variables (eVars)
topic: Developer and implementation
uuid: 5aac2164-b71b-426b-84da-346fa2624aff
index: y
internal: n
snippet: y
---

# Conversion variables (eVars)

The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports.

eVars are best used to measure cause and effect, such as:

* Which internal campaigns influenced revenue 
* Which banner ads ultimately resulted in a registration 
* The number of times an internal search was used before making an order

>[!IMPORTANT]
>
>When implementing Analytics, it is important to know which eVars you will use, and how many. You should also understand how to configure those eVars in the Admin Console. For detailed information about eVars, see [Conversion Variables (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) in the Analytics Help and reference documentation.

An eVar can be visit-based and function similarly to cookies. Values passed into eVar variables follow the user for a predetermined period of time.

When an eVar is set to a value for a visitor, Adobe automatically remembers that value until it expires. Any success events that a visitor encounters while the eVar value is active are counted toward the eVar value.

>[!NOTE]
>
>Only a single value can be stored in an eVar in an image request. If multiple values are desired in an eVar value, we recommend that you implement [List variables](listN.md#concept_74541AAC659740B9A6B7CA70FBB33D40) (list vars).

For more information about variables, see:

* [Variables for Analytics Implementation and Reporting](../js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) in this help 
* [Variables - How They Are Used in Reporting](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html) in the Analytics help 
* [Page Variables](https://marketing.adobe.com/resources/help/en_US/sc/implement/page-variables.html#) in this help 
* [Campaign variable](campaign.md#concept_C7BF7B8A69D048A6AB482052A98A91F8) in this help 
* [Products Variable](products.md#concept_A4007F6307E4419DAA65E1668A8FEBA2) in this help 
* [Products Variable](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) in the Mobile SDK documentation

