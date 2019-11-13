---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.linkTrackEvents

The  variable is a comma-separated list of events that are sent with a custom, exit, or download link. The `linkTrackEvents` parameter should include each event you want to track with every file download, exit link, and custom link. When one of these link types occur, the current value of each variable identified is tracked. This variable is only considered if `linkTrackVars` contains "events." 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Conversion  | "None"  |

If an event is not in `linkTrackEvents`, it is not sent to Analytics, even if it is populated in the `onClick` event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 

```

The values of [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link. The settings for both affect every file download, exit link, and custom link. Instances of each variable and event can be inflated in situations where the variable (or event) applies to the current page, but not the specific file download, exit link or custom link.

To ensure that the proper variables are set with custom link code, Adobe recommends setting *`linkTrackVars`* and *`linkTrackEvents`* within the custom link code, as follows:

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

*Note: If `linkTrackVars` (or `linkTrackEvents`) is null (or an empty string such as ""), all Analytics variables (or events) that are defined for the current page are tracked. In other words, all variables that have values would be sent with link data. This will most likely inflate instances of each variable. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating `linkTrackVars` and `linkTrackEvents` in the [!UICONTROL onClick] event of a link that is used for link tracking.*

All variables that should be sent with link data (custom, exit, and download links) should be listed in `linkTrackVars`. If `linkTrackEvents` is used, `linkTrackVars` should contain "events." 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Any  | "None"  |

When populating `linkTrackEvents`, do not use the 's.' prefix for variables. For example, instead of populating it with "s.event1," you should populate it with "event1." The following example illustrates how it should be used.

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

In the first link, notice that the events variable retains the value that was set before the link was clicked. This allows event1 to be sent with the custom link. In the second example, the link to event2 is not recorded because it is not listed in `linkTrackEvents`.

To avoid confusion and potential problems, Adobe recommends populating [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` in the `onClick` event of a link that is used for link tracking.

## Syntax and Possible Values

The *`linkTrackEvents`* variable is a comma-separated list of events (no spaces).

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Only event names are allowed in `linkTrackEvents`. These events are listed in [Events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). If a space appears before or after the event name, the event cannot be sent with any link image requests.

## Examples

To track `prop1`, `eVar1`, and `event1` with every file download, exit link, and custom link, use the following settings within the global JS file:

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**More examples**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* The JavaScript file only uses `linkTrackEvents` if `linkTrackVars` contains the "events" variable. "events" should be included in `linkTrackVars` only when `linkTrackEvents` is defined.

* Beware if an event is fired on a page, and is listed in `linkTrackEvents`. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the `t()` function).

* If `linkTrackEvents` contains spaces between event names, the events are not recorded.
