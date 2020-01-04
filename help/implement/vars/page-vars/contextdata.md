---
title: contextData
description: Context data variables let you define custom variables on each page that can be read by processing rules.
---

# contextData

Context data variables let you define custom variables on each page that can be read by processing rules.

Instead of explicitly assigning values to props and eVars in your code, you can send data in context data variables that are mapped using processing rules. Processing rules provide a powerful interface to make changes to data as it is received. Based on the values sent in context data, you can set events, copy values to eVars and props, and execute additional conditional statements. Using context data variables helps prevent making code updates to support different report suite configurations.

> [!IMPORTANT] Context data variables are discarded after processing rules run. If you do not have processing rules active that place values into variables, that data is lost.

## Syntax - Adobe Experience Platform Launch

Launch does not have a dedicated location to define context data variables. Use the Custom Code Editor in a rule using AppMeasurement syntax.

## Syntax - JavaScript AppMeasurement and Launch Custom Code

Context data variables require variable name and a value assigned to it.

```js
s.contextData['example-variable'] = "Example value";
```

## Use

Use the following steps to use context data variables in reporting:

1. Update your implementation to set context data variable names and values.
2. Log in to Adobe Analytics and go to Admin > Report Suites.
3. Select the desired report suite, then go to Edit Settings > General > Processing Rules.
4. Create a processing rule that sets an Analytics variable to the context data variable value.
5. Save changes.

Processing rules immediately take effect once saved. They do not apply to historical data.


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
   <td colname="col2"> <p>Context data variable names can contain only alphanumeric characters, underscores and dots. Any additional characters are stripped out. Context cata variables do not have a numeric designation. Rather, they are named. </p> <p>For example, the context data variable <code> login_page-home </code> automatically becomes <code> login_pagehome </code>. All data sent to the <code> login_page-home </code> variable is allocated under <code> login_pagehome </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Namespace </p> </td> 
   <td colname="col2"> <p>A good practice is to prefix your variables with your company name, site name, or a similar value to make sure the name is unique across your report suite. </p> <p>Context data variables can be named similar to other JavaScript variables. Be aware that the namespace <code> a.* </code> is reserved for use by Adobe products in context variable names. For example, the AppMeasurement Library for iOS uses <code> a.InstallEvent </code> to measure application installations. </p> </td> 
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

For an example, see [Copy a Context Data Variable to an eVar](https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_copy_context_data.html) in Analytics Reference.

> [!NOTE] Context data variables are not case sensitive. For example, the following 2 variables are effectively identical:
>```
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>```
>and
>```
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```