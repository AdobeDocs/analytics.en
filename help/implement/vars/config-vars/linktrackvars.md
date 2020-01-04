---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---

# s.linkTrackVars

The  variable is a comma-separated list of variables that are sent with custom, exit, and download links.

The [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) parameter should include each variable that you want to track with every file download, exit link, and custom link. 

The settings for `linkTrackVars` and `linkTrackEvents` within the JS file affect every file download, exit link, and custom link. Instances of each variable and event can be inflated in situations where the variable (or event) applies to the current page, but not the specific file download, exit link,or custom link.

To ensure that the proper variables are set with custom link code, Adobe recommends setting `linkTrackVars` and `linkTrackEvents` within the custom link code, as follows:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 

```

In the above example, the value for prop1 is set within the custom link code itself. The value of prop2 comes from the current value of the variable as set on the page.

The values of `linkTrackVars` and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

*Note: If `linkTrackVars` (or `linkTrackEvents`) is null (or an empty string such as ""), all Analytics variables (or events) that are defined for the current page are tracked. In other words, all variables that have values would be sent with link data. This will most likely inflate instances of each variable. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating `linkTrackVars` and `linkTrackEvents` in the [!UICONTROL onClick] event of a link that is used for link tracking.*

All variables that should be sent with link data (custom, exit, and download links) should be listed in `linkTrackVars`. If `linkTrackEvents` is used, `linkTrackVars` should contain "events." 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Any  | "None"  |

When populating `linkTrackVars`, do not use the 's.' prefix for variables. For example, instead of populating `linkTrackVars` with "s.prop1," you should populate it with "prop1." The following example illustrates how `linkTrackVars` should be used.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 

```

Because the link to google.com is an exit link (unless you are Google), event1 and eVar1 are sent with the exit link data, increasing the instances associated with eVar1 and the number of times event1 is fired. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of eVar1 at the time that `tl()` is called.

## Syntax and Possible Values

The `linkTrackVars` variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Use 'eVar1' instead of 's.eVar1.'

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

The `linkTrackVars` variable may contain only variables that are sent to [!DNL Analytics], namely: `events`, `campaign`, `purchaseID`, `products`, `eVar1-75`, `prop1-75`, `hier1-5`, `channel`, `server`, `state`, `zip`, and `pageType`.

## Examples

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* If `linkTrackVars` is blank, all variables that have values are tracked with all server calls.
* Any variable listed in `linkTrackVars` that has a value at the time of any download, exit, or custom link, are tracked.
* If `linkTrackEvents` is used, `linkTrackVars` must contain "events." 

* Do not use the "s." or "s_objectname." prefix for variables.

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
