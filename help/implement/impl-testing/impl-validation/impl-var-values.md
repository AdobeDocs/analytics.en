---
description: Ensure that the variables that are populated from server scripting or code cannot output any quotation marks that interfere with the values.
keywords: Analytics Implementation
seo-description: Ensure that the variables that are populated from server scripting or code cannot output any quotation marks that interfere with the values.
seo-title: Variables and values
solution: Analytics
title: Variables and values
topic: Developer and implementation
uuid: 2ff4857a-9451-4794-9146-f417abd1d1ba
---

# Variables and values

Ensure that the variables that are populated from server scripting or code cannot output any quotation marks that interfere with the values.

 For instance:

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 

```

Ensure that the values of the variables do not exceed their maximum limits, specified in this document. Additional characters are cropped at the data collection servers. They may interfere with the total length, increase bandwidth unnecessarily, and may cause other issues.

Do not use $, ™, ®, ©, or commas (,) in the products variable. Generally, these are not useful in any [!DNL Analytics] variables and may interfere with the ability to interpret or export fields. The best practice is to limit characters to the first 127 ASCII characters.

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. Ensure that the case of all [!DNL Analytics] variables and functions are maintained, as shown below.

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 

```

Page names are case sensitive, and differences create additional page records. "Home" and "home" are two different pages within [!DNL Analytics].

>[!NOTE]
>
>Multiple page records cannot be combined within reports.

Validate that links are reported in the [!UICONTROL Custom Links] report. Ensure that the correct parameters are passed to the [!UICONTROL tl] function. For more information on [!UICONTROL custom links], see [Link Tracking](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E). 
