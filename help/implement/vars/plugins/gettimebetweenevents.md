---
title: getTimeBetweenEvents
description: Measure the amount of time between two events.
exl-id: 15887796-4fe4-4b3a-9a65-a4672c5ecb34
---
# Adobe plug-in: getTimeBetweenEvents

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Account Manager. They can arrange a meeting with a consultant for assistance.

The `getTimeBetweenEvents` plug-in allows you to track the amount of time between any two Analytics events, including shopping cart and custom events. It is useful in tracking the amount of time it takes for a checkout process to complete, or any other process that you want to measure time. This plug-in is unnecessary if you don't have any conversion processes that you want to measure how long they take.

## Install the plug-in using tags in Adobe Experience Platform

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getTimeBetweenEvents
1. Save and publish the changes to the rule.

## Install the plug-in using custom code editor

If you do not want to use the plug-in extension, you can use the custom code editor.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click on the desired property.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.
1. Open the custom code editor and paste the plug-in code provided below into the edit window.
1. Save and publish the changes to the Analytics extension.

## Install the plug-in using AppMeasurement

Copy and paste the following code anywhere in the AppMeasurement file after the Analytics tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)). Preserving comments and version numbers of the code in your implementation helps Adobe with troubleshooting any potential issues.

```js
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Use the plug-in

The `getTimeBetweenEvents` function uses the following arguments:

* **`ste`** (required, string): Start timer events. A comma-delimited string of Analytics events to "start the timer".
* **`rt`** (required, boolean): Restart timer option. Set to `true` if you want to restart the timer every time the `events` variable contains a start timer event. Set to `false` if you don't want the timer to restart when it sees a start timer event.
* **`stp`** (required, string): Stop timer events. A comma-delimited string of Analytics events that "stop the timer".
* **`res`** (required, boolean): Reset timer option. Set to `true` if you want to record the time since the timer started AND reset the timer after it stops. Set to `false` if you want to record the time but not stop the timer. If set to `false`, the timer continues to run after the events variable records a stop event.

  >[!TIP]
  >
  >If you set this argument to `false`, setting the `rte` argument below is highly recommended.
* **`cn`** (optional, string): The cookie name where the time of the first event is stored. Defaults to `"s_tbe"`.
* **`etd`** (optional, integer): The expiration time for the cookie in days. Set to `0` to expire at the end of the browser session. Defaults to 1 day when not set.
* **`fmt`** (optional, string): The format of the time that the number of seconds is returned in (defaults to nothing)
  * `"s"` for seconds
  * `"m"` for minutes
  * `"h"` for hours
  * `"d"` for days
  * When not set, the return value's format is based on the following rules:
    * Anything less than a minute is rounded to the closest 5 second benchmark. For example, 10 seconds, 15 seconds
    * Anything between a minute and an hour is rounded to the closest 1/2-minute benchmark. For example, 30.5 minutes, 31 minutes
    * Anything between an hour and a day is rounded to the closest quarter-hour benchmark. For example, 2.25 hours, 3.5 hours
    * Anything greater than a day is rounded to the closest day benchmark. For example, 1 days, 3 days, 9 days
* **`bml`** (optional, number): The length of the rounding benchmark according to the format of the `fmt` argument. For example, if the `fmt` argument is `"s"` and this argument is `2`, the return value is rounded to the closest 2-second benchmark. If `fmt` argument is `"m"` and this argument is `0.5`, the return value is rounded to the closest half-minute benchmark.
* **`rte`** (optional, string): Comma-delimited string of Analytics events that remove or delete the timer. Defaults to nothing.

Calling this function returns an integer representing the amount of time between the start timer event and stop timer event in the desired format.

## Example Calls

```js
// The timer starts or restarts when the events variable contains event1
// The timer stops and resets when the events variable contains event2
// The timer resets when the events variable contains event3 or the visitor closes their browser
// Sets eVar1 to the number of seconds between event1 and event2, rounded to the nearest 2-second benchmark
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");

// The timer starts when the events variable contains event1. It does NOT restart with subsequent hits that also contain event1
// The timer records a "lap" when the events variable contains event2. It does not stop the timer.
// The timer resets when the events variable contains event3 or if more than 20 days pass since the timer started
// The timer is stored in a cookie labeled "s_20"
// Sets eVar4 to the number of hours between event1 and event2, rounded to the nearest 90-minute benchmark
s.eVar4 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");

// Similar to the above timer in eVar4, except the return value is returned in seconds/minutes/hours/days depending on the timer length.
// The timer expires after 1 day.
s.eVar4 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

## Version History

### 3.0 (March 19, 2021)

* Added version number as context data.

### 2.1 (May 26, 2018)

* Accommodates changes made to the new version of the `formatTime` plug-in.

### 2.0 (April 6, 2018)

* Complete rewrite/reanalysis of plug-in.
