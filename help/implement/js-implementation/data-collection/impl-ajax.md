---
description: Implementing with AJAX is exactly like deploying code on a standard HTML page.
keywords: Analytics Implementation
solution: Analytics
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

