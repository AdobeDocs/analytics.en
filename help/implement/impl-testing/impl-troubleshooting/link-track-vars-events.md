---
description: The key to a successful link tracking implementation is understanding the s.linkTrackVars and s.linkTrackEvents variables. This lets you pass custom variable values on user actions.
keywords: Analytics Implementation
seo-description: The key to a successful link tracking implementation is understanding the s.linkTrackVars and s.linkTrackEvents variables. This lets you pass custom variable values on user actions.
seo-title: Using s.linkTrackVars and s.linkTrackEvents
solution: Analytics
title: Using s.linkTrackVars and s.linkTrackEvents
topic: Developer and implementation
uuid: f6b7019b-987b-4b7d-a446-80205f7cc36c
index: y
internal: n
snippet: y
---

# Using s.linkTrackVars and s.linkTrackEvents

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
