---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.linkTrackVars

The  variable is a comma-separated list of variables that are sent with custom, exit, and download links. 

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events." 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Any  | "None"  |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

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

Because the link to google.com is an exit link (unless you are Google), event1 and eVar1 are sent with the exit link data, increasing the instances associated with eVar1 and the number of times event1 is fired. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## Syntax and Possible Values

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Use 'eVar1' instead of 's.eVar1.'

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

The *`linkTrackVars`* variable may contain only variables that are sent to [!DNL Analytics], namely: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`*, *`zip`*, and *`pageType`*.

## Examples

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls. 
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked. 
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events." 

* Do not use the "s." or "s_objectname." prefix for variables.
