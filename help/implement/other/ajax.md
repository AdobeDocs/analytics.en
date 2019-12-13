---
description: Implementing with AJAX is exactly like deploying code on a standard HTML page.
keywords: Analytics Implementation
title: Implementing with AJAX
topic: Developer and implementation
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
---

# Implementing with AJAX

Implementing with AJAX is exactly like deploying code on a standard HTML page.

The business has questions that need answers, the needs are assessed and variables assigned. The design is then applied and deployed. These concepts should be familiar if you have already been through the initial stages of implementation.

## Designing the Solution {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

The difference when throwing [!UICONTROL AJAX] into the mix is first understanding the level of detail that needs to be gathered. The potential of content changing on the page (macro-level) or tracking attributes of the application (micro-level) determines which variables need to be set and which method of sending data to Adobe works best.

## Deploying the Code {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

There are two functions in the JavaScript code that allow you to send data. There are some distinct guidelines that should be followed to know which method should be used to send data.
If an image request was previously made on the same page, you must first clear the values of the previously-set variables. Use the `clearVars()` funtion in [!DNL AppMeasurement] for JavaScript, or write a simple JavaScript function to clear the variables if you are using H code. Set the values appropriate for the changed content, namely the *`pageName`* variable. After the variables are set call the *`t()`* function.

> [!NOTE] Before you call `s.t()`, you must clear any values on the s object that you do not want to persist. if you are using [!DNL AppMeasurement] for JavaScript, you can call `s.clearVars()`. If you are using H code, write a simple routine to set variables to an empty string.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 

```

If an image request was previously made on the same page, clear the values of the previously-set variables. This can be accomplished by:

* Writing a simple JavaScript function to clear the Adobe variables.
* Set the *`linkTrackVars`* and *`linkTrackEvents`* variables if you have not already done it in the [!DNL s_code.js] file.

* Set the values appropriate for the changed content, namely the *`pageName`* variable.
* After the variables are set, call the *`tl()`* function.

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```

## AJAX-Track rich media applications

AJAX is an emerging concept in web design that uses multiple technologies to create and manage dynamic content on Web pages.

The need to track user interaction with [!UICONTROL AJAX] and other rich media applications is paramount to analytics success and realization of the return on investment in the Web design. The focus of this white paper is to provide recommendations for tracking rich Internet applications, specifically those that use [!UICONTROL AJAX].

## Rich Internet Applications (RIA) {#section_CDCAFC4E05B44985BCBF34DFCB35DCA6}

Rich Internet Applications (RIAs) are changing the face of the Web. They bridge the gap between the promise of on-demand technologies for the masses and realistic user experiences. RIAs have been maturing for years. The biggest leaps forward have occurred with wide-scale adoption of browsers, which support the underlying technologies that power these applications. While RIA has many forms and supporting technologies, the most common, and perhaps most widely adopted, are AJAX and Flash. It is important to understand that the technology is not what defines an RIA, but its usability and application.

## What to Track {#section_E96EC5127E554B8384FD0A7A0B3118DF}

One of the most commonly asked questions with RIA is how to track micro-level activity separate from macro-level activity, and when it is appropriate to do either. For example, say you have an application that allows customers to uniquely configure a product. The application may have significant steps the users are exposed to. Are these steps considered page views? In addition, there are micro-level activities within each step. Should these activities be tracked as page views?

What if you want to understand the flow between activities, or which features get the most activity? The trouble with RIA is that each application is unique. They are designed to mimic realistic actions, and since actions are relative to the situation, the possibilities are endless. However, most applications have a few major components: milestone steps, features, and micro-level actions within features. So, while each application requires some consideration as to what specifically should be measured, there are some generalizations that can be applied to RIA tracking.
Macro-level activity usually constitutes the loading of the application. This provides information on visits, visitors, instances, value to future actions, and so forth. It can, and should, also represent major steps in the process. A good rule of thumb is that if an RIA action changes the application more than 50% (or whatever is considered significantly changing the user experience or content), then it is macro-level, and should be tracked as a page view.
Micro-level activity includes any changes less than 50% (or not considered as significantly changing the user experience or content). Toggling between color selections, for instance, would be considered micro-level activity. Adobe recommends that micro-level tracking be related to features. For example, in the case of toggling between colors, is it really important to understand which colors were considered? Or is it more important to know that the color selection feature was used? Perhaps both are important, and if so, capture both, but when measuring the effectiveness of RIA, consider the feature level activity as being more valuable.

All micro-level activity should be tracked as custom links with specifics measured through associated traffic variables (props and eVars if the use needs to be measured against success events). This ensures that page views are not inflated by micro-level activity, and allows for path analysis through the traffic variable.

## What to Analyze {#section_56824EF675874BA99127A566F6B1383F}

It is important to understand how effectively your RIA is driving success. Success is most commonly measured through conversions. A macro-level analysis provides insight into RIA effectiveness as a whole. Micro-level analysis may provide insight into which features help drive conversion.

You should measure efficiency of your RIA. This is an analysis of micro-level activity relative to the RIA macro metrics. Do users go through more steps than necessary to arrive at the same goal? Analysis metrics might include visits/features activity; page views/feature activity, visitors/feature activity, and so forth.

Conduct analysis on path flow and fall out. Are users avoiding the RIA and finding another path to the goal? Run fallout reports built around the site and RIA flow. Run path analysis from landing pages to gauge the true traffic patterns. Look at barriers and incentives to guide users toward the goal.

## Suggested Metrics {#section_AB7047D6C74740C6B6E47ED93602DB07}

* RIA Visits 
* RIA Visitors 
* RIA Page Views 
* RIA Feature Activity (Custom Links) measure click activity by feature

## Suggested Analysis {#section_5BE0FB9ECA3049E5965BEAD733DA5B6E}

* RIA Feature Activity / RIA Page Views 
* RIA Feature Activity / RIA Visits - 
* RIA Page Views / Success Metric - Conversion Ratio: measures application effectiveness 
* Total RIA Activity / Success Metric - Conversion Ratio: measures application efficiency 
* Feature RIA Activity / Success Metric - Conversion Ratio: measures application feature efficiency 
* Path Flow to and from RIA 
* Fallout Rates through RIA conversion process
