---
description: Context data variables let you define custom variables on each page that can be read by processing rules.
keywords: Analytics Implementation;contextdata;s.contextdata
seo-description: Context data variables let you define custom variables on each page that can be read by processing rules.
seo-title: Context data variables
solution: Analytics
subtopic: Variables
title: Context data variables
topic: Developer and implementation
uuid: 4b215803-99d4-46f2-b3c1-e78558987764
index: y
internal: n
snippet: y
---

# Context data variables

Context data variables let you define custom variables on each page that can be read by processing rules.

Instead of explicitly assigning values to props and eVars in your code, you can send data in context data variables that are mapped using processing rules. Processing rules provide a powerful graphical interface to make changes to data as it is received. Based on the values sent in context data, you can set events, copy values to eVars and props, and execute additional conditional statements.

>[!NOTE]
>
>Context data variables are not case sensitive. For example, the following 2 variables are effectively identical: >
>```>
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>
>```>
>and 
>
>```>
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```>

Using context data helps prevent you from making code updates to support different report suite configurations.

For example, you can define the following *`s.contextData`* variable:

```
s.contextData['myco.rsid'] = 'value'
```

Using processing rules you can add a condition that checks for a `myco.rsid` context data variable. When this variable is found, you can add an action to copy it to a prop or eVar.

Context data variables can also be defined directly in the processing rules interface to temporarily store a value, or to collect values from a context data variable you know will be used on the report suite. For example, if you need to swap two values, you could create a context data variable to store a value during the swap.

Since processing rules are applied only when data is collected, it is important to set up processing rules before you start sending context data. Context data values that are not read by processing rules when a hit is processed are discarded.

## Rules {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Rule </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Supported names and characters </p> </td> 
   <td colname="col2"> <p>Context data variable names can contain only alphanumeric characters, underscores and dots. Any additional characters are stripped out. Context cata variables do not have a numeric designation. Rather, they are named. </p> <p>For example, the context data variable <span class="codeph"> login_page-home </span> automatically becomes <span class="codeph"> login_pagehome </span>. All data sent to the <span class="codeph"> login_page-home </span> variable is allocated under <span class="codeph"> login_pagehome </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Namespace </p> </td> 
   <td colname="col2"> <p>A good practice is to prefix your variables with your company name, site name, or a similar value to make sure the name is unique across your report suite. </p> <p>Context data variables can be named similar to other JavaScript variables. Be aware that the namespace <span class="codeph"> a.* </span> is reserved for use by Adobe products in context variable names. For example, the AppMeasurement Library for iOS uses <span class="codeph"> a.InstallEvent </span> to measure application installations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL Limits for Internet Explorer </p> </td> 
   <td colname="col2"> <p>You might encounter a older URL limitation for Internet Explorer 6 and 7, where URLs are truncated at 2000 bytes. You can use the <span class="keyword"> DigitalPulse </span> debugger to determine the size of a URL string. </p> <p>With the recent updates to AppMeasurement (September 2014),HTTP POST is used with Internet Explorer 8+, which eliminates truncation issues. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supported AppMeasurement version </p> </td> 
   <td colname="col2"> <p>Context data variables require at least H23 code or higher. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sending Context Data on a Track Link Call {#section_35EBE5D1CF29427598BD4B2165CE64FC}

Include `ContextData` + the name of the variable that you would like included in `s.linkTrackVars`:

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 

```

## Examples {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possible ways to replace implementation of the *`s.pageName`* variable, assuming that processing rules are set up correctly for each:

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

Other examples to implement context data variables:

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

For an example, see [Copy a Context Data Variable to an eVar](https://marketing.adobe.com/resources/help/en_US/reference/?f=processing_rules_copy_context_data) in Analytics Reference. 
