---
title: Troubleshoot JavaScript implementation
description: Learn about common issues for troubleshooting your JavaScript implementation.
---

# Troubleshoot JavaScript implementation

The following are several reasons why your organization might have issues with correctly getting data into Adobe Analytics.

## Using quotes

When you input values into a variable, there are a few best practices to follow.

You can use single quotes or double quotes, make sure you are consistent. If you are using single quotes, always use single quotes. If you are using double quotes, always use double quotes. Both of the examples below are correct.

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

Make sure that you have smart quotes turned off. If you are using single quotes, and you have an apostrophe in the variable value, JavaScript interprets the apostrophe as a single quote. This means it is the end of the string. Consider the following example: 

```js
s.pageName='John's Home Page'
```

In this case, JavaScript would interpret the apostrophe (which is also a single quote) in "John's" to be the end of the string. Since ''s Home Page" has no meaning in JavaScript, it causes an error that prevents the image request from occurring. Either of the following examples would work: 

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

In the first example, you can escape the apostrophe by inserting a backslash (\) immediately before it. This tells JavaScript that the apostrophe is not ending the string, but rather is part of it. The string then ends as intended, at the closing single-quote. The second example uses double-quotes around the entire string. In this case, a single-quote cannot indicate the end of the string. The same is true if a double-quote is part of the string. A value of s.pageName="Team Says "We Win!"" would be incorrect because of the use of double-quotes within the string, as well as surrounding it. This would be correct if entered as s.pageName="Team Says \"We Win!\"".

## Common syntax mistakes

The following table shows the difference between correct and incorrect code mistakes.

|  Incorrect  | Correct  |
|---|---|
|  prop1  | s.prop1 (uses "s.")  |
|  s.evar1  | s.eVar1 (uses correct capitalization)  |
|  s.pagetype='errorpage';  | s.pageType='errorPage'; (uses correct capitalization)  |
|  s.tl(this,o,pageA)  | s.tl(this,'o','pageA'); (correct usage of single quotes)  |
|  s.events='event1'; s.events='event2';  | s.events='event1,event2'; (correct format)  |
|  s.pageName="John" (smart quotes on)  | s.pageName="John" (smart quotes off)  |
|  s.products="shoes,UX4879,1,19.99"  | s.products="shoes;UX4879;1;19.99" (uses semicolons, not commas)  |
|  s.products=";MacBook Air;1;$1999.99"  | s.products=";MacBook Air;1;1999.99" (does not use dollar signs)  |
|  s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183"  | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95" (round or truncate long prices)  |
|  var s_account="rsid1, rsid2"  | var s_account="rsid1,rsid2" (no space between report suite IDs when doing multi-suite tagging)  |
|  s.events="event1, event2"  | s.events="event1,event2" (no space between event IDs when doing multi-event tagging)  |
|  s.products="product name"  | s.products=";product name" (semicolon used when no product category is listed)  |

### Additional Notes {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

Keep the closing HTML comment at the very end of the Adobe code (even if you are using the NOSCRIPT part of the script).

## Plug-ins {#section_53650E52D6A54A4795F95E491E7548D1}

Some customers implement plug-ins to enhance their Adobe experience. When you replace your code, do not forget that you have plug-ins as part of that code. The code created in the [!UICONTROL Code Manager] does not have any plug-in code with it, so all plug-ins need to migrate manually to the newer code base. Make a copy of your existing code just in case something happens, and you need to revert to your previous code.

## Using white space in variable values

In HTML there are several characters that create whitespace.

 These include a space, a tab, and a carriage return (or linefeed). Consider the following example: 

```js
<head> 
 <title> 
   Home Page 
 </title> 
</head> 
<body> 
<script language="javascript"> 
 s.pageName=document.title 
</script> 

```

In this case, document.title populates [!UICONTROL s.pageName], which should receive a value of "Home Page." Notice the space before "Home Page." Not all browsers interpret this white space in the same way. The result may be either of two examples below: 

```js
s.pageName="Home Page"
```

```js
s.pageName="        Home Page"
```

The first value displays correctly, but the second displays white space before the text. [!DNL Analytics] treats these as distinct values for the [!UICONTROL s.pageName] variable. The [!DNL Analytics] interface strips the leading white space from the second value. The result is a report that displays as shown below.

![](assets/white_space.jpg)

This implementation error causes your variable values to be fragmented across multiple line items. [!DNL SAINT] does not allow leading white space in a key value. This means that it cannot be used to group multiple line items as a work-around if this issue is affecting your site. The only way to fix the problem is to pre-process the desired variable value (in this case, the document.title property) to remove any leading (or trailing) white space.

The example above uses the [!UICONTROL s.pageName] variable with the document.title property. Adobe does not recommend using document.title as the page name, nor does this issue only affect the [!UICONTROL s.pageName] variable. Any variable that has leading/trailing white space in its value can be affected.

## Using s.linkTrackVars and s.linkTrackEvents

The key to a successful link tracking implementation is understanding the s.linkTrackVars and s.linkTrackEvents variables. This lets you pass custom variable values on user actions.

 If you are implementing custom link tracking and are setting [!UICONTROL custom] variables and *`events`*, make sure that your [!UICONTROL s.linkTrackVars] variable contains a comma-separated list of all variables that you are passing, including the *`events`* variable. Make sure that [!UICONTROL s.linkTrackEvents] includes a comma-separated list of all events that you are passing.

Setting [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] does not actually set these variables/events, it only prepares the [!DNL Analytics] code to do so. You still need to set the variables manually, as shown in the example below:

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 

```

Notice that events is listed in the [!UICONTROL s.linkTrackVars] variable. The individual events that may be passed are included in the [!UICONTROL s.linkTrackEvents] variable and are also included within [!UICONTROL s.events] later in the function. Each of the variables that are passed are listed in [!UICONTROL s.linkTrackVars] before they are populated later in the function. Also, "event9″ has been included in [!UICONTROL s.linkTrackEvents], but has not been included in [!UICONTROL s.events]. It is not recorded, but could be recorded if the user had chosen to set s.events="event5,event9."

Automatic file download and [!UICONTROL Exit] link tracking work differently. The [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] are included in the standard [!DNL s_code.js] file, and both are set to none. These variables are typically left set to none in the [!DNL s_code.js] file so that automatic link tracking, unlike [!UICONTROL custom link tracking], uses the [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] values that you set in the global JavaScript file. They also pass whatever the existing values of those variables are whenever a file download or [!UICONTROL Exit] link is recorded.

Consider the example where s.channel="Home" when the page loads, and where s.linkTrackVars="channel" in your [!DNL s_code.js] file. If a user clicks to download a file, automatic file download tracking passes data into [!DNL Analytics], including the value of [!UICONTROL s.channel] that was set on page load. "Home" is passed a second time, leading to inflation in page view data for this value in the [!UICONTROL Site Sections] report.

Adobe strongly recommends leaving the [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] set to "none" in the global JavaScript file and setting them explicitly as necessary with your [!UICONTROL custom link tracking] implementation.

## Setting the PageType variable incorrectly

The pageType variable is used only to designate a 404 (Page Not Found) error page.

 It has only one possible value, which is errorPage.

```js
pageType="errorPage"
```

On a 404 error page, the *`pageName`* variable should not be populated. The *`pageType`* variable should be set only on a designated 404 error page. Any page containing content should never have a value in the *`pageType`* variable. For pages containing content, you can set the variable as shown below: 

```js
pageType=""
```

It is best to delete the variable completely from pages containing content. This practice is recommended to avoid confusion regarding the purpose of the variable.

## Common mistakes in the Products variable

The s.products variable may be the most syntactically complex variable used by data collection.

 Commas, semi-colons, pipes, and equals signs all play specific roles in the variable. It has no overall maximum length, but each individual product entry cannot be longer than 100 bytes (including multi-byte characters). Mistakes in implementation of this variable are understandable, but unfortunately for developers, [!UICONTROL s.products] is often a site's most important variable because it makes possible the tracking of revenue, units, product names, and so forth.

Here are a few extremely easy-to-make mistakes that can cause issues on any implementation.

Make sure that your [!UICONTROL category], [!UICONTROL product name], and [!UICONTROL revenue] totals are devoid of commas and semi-colons. The comma is used to separate entries in the [!UICONTROL s.products] string. This happens when you have two products in the same transaction, the semi-colon is used to delimit fields within an entry. If you use a comma or semi-colon in any other way, data collection assumes that you are separating product entries. Consider the following example:

```js
s.products="widgets;large widget, 40′x40′;1;19.99,wugs;tiny wug;2;1,999.98";
```

In this implementation, the developer probably intended for data collection to read this as shown below:

Category 1: widgets

Product 1: large widget, 40′x40′

Units 1: 1

Revenue 1: 19.99

Category 2: wugs

Product 2: tiny wug

Units 2: 2

Revenue 2: 1,999.98

Note the commas in the Product 1 and Revenue 2 entries. These indicate a new product entry. Data collection would interpret the above as:

Category 1: widgets

Product 1: large widget

Category 2: 40'x40'

Product 2: 1

Units 2: 19.99

Category 3: wugs

Product 3: tiny wug

Units 3: 2

Revenue 3: 1

Category 4: 999.98

A mistake like this often results in unexpected numerical values in the [!UICONTROL Products] report, because the units field is recorded as the product name. If you see invalid product names in your [!UICONTROL Products] report, review your [!UICONTROL s.products] variable implementation for misuse of reserved characters, like the comma.

Your product and category names should not contain unsupported characters. This can be especially difficult in the [!UICONTROL s.products] string, because product names are often likely to contain characters such as ™, ©, and ®. These characters need to be stripped out of the product and category values before they are placed into [!UICONTROL s.products]. You also need to ensure that currency symbols are not included in your revenue values. Supported characters are numbers 1-127 from the ASCII table.

If you are not passing a product category in the product string, make sure to include a semi-colon (;) where the product category is normally displayed, as shown below: 

```js
s.products=";product name"
```

In this case, the semi-colon represents a placeholder for the product category. If the semi-colon is left out of the product string, then "product name" would be counted as the category, the number of units to be counted as the product name, the revenue to be counted as the units, and so on.
