---
description: The apl (or appendList) plug-in lets you append a value to any delimited lists, with the option of a case-sensitive or case-insensitive check to ensure that the value does not already exist in the list. The APL plug-in is referenced by several standard plug-ins but can be used directly in a variety of situations.
keywords: Analytics Implementation
seo-description: The apl (or appendList) plug-in lets you append a value to any delimited lists, with the option of a case-sensitive or case-insensitive check to ensure that the value does not already exist in the list. The APL plug-in is referenced by several standard plug-ins but can be used directly in a variety of situations.
seo-title: appendList
solution: Analytics
subtopic: Plug-ins
title: appendList
topic: Developer and implementation
uuid: ddfda2fb-7451-4aae-a7b8-eb28b6b94193
index: y
internal: n
snippet: y
---

# appendList

The apl (or appendList) plug-in lets you append a value to any delimited lists, with the option of a case-sensitive or case-insensitive check to ensure that the value does not already exist in the list. The APL plug-in is referenced by several standard plug-ins but can be used directly in a variety of situations.

This plug-in is useful for:

* Adding an event to the current events variable 
* Adding a value to a list variable without duplicating a value in the list 
* Adding a product to the current products variable based on some page logic 
* Adding values to the parameters *`linkTrackVars`* and *`linkTrackEvents`*

**Use Case 1** 

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scenario </p> </td> 
   <td colname="col2"> <p>Add <span class="term"> event1 </span> to the current events variable while ensuring the event isn't duplicated. </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Results </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Use Case 2** 

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scenario </p> </td> 
   <td colname="col2"> <p>Add the value <span class="term"> history </span> to the list variable <span class="varname"> prop1 </span>, with <span class="term"> history </span> and <span class="term"> History </span> considered the same value. </p> <p>s.prop1="Science,History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Results </p> </td> 
   <td colname="col2"> <p>s.prop1="Science,History" </p> <p> <span class="term"> history </span> is not added because <span class="term"> History </span> is already in the list. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The following instructions require you to alter the data collection code on your site. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Implementation {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

Follow these steps to implement the APL plug-in.

1. Request the plug-in code from Customer Care or your currently assigned Adobe consultant. 
1. Add call(s) to the API function as needed within the *`s_doPlugins`* function

Here is how the code might look on your site:

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**Supported Browsers**

This plug-in requires that the browser supports JavaScript version 1.0.

**Plug-in Information** 

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Plug-in Information </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Parameters </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L= source list, empty list is accepted </p> <p> v = value to append </p> <p> d = list delimiter </p> <p> u (optional, defaults to 0) Unique value check. 0=no unique check, value is always appended. 1=case-insensitive check, append only if value isn't in list. 2=case-sensitive check, append only if value isn't in list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Return Value </p> </td> 
   <td colname="col2"> <p>original list, with appended value if added </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage Examples </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

The source list L can be an empty list, such as *`L=""`*. The returned value will either be an empty list, or a list of one value.

**Plug-in Code**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 s.split

```

