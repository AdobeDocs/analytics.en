---
title: Implementing with AJAX
description: Learn how to implement Adobe Analytics on a site using AJAX.
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
---
# Implementing with AJAX

AJAX is a practice of using JavaScript and HTML to clear and generate content without loading a new page.

Adobe Analytics normally relies on pages reloading to reset the Analytics tracking object. Every time you navigate to a different URL, all Analytics variables reset and can be defined again. When using AJAX on your site, adjust your implementation around the lack of page refreshes to make sure data does not incorrectly persist between hits.

Once you have measures in place to clear variable values, implementing Adobe Analytics on sites that use AJAX is mostly the same as other implementation methods.

## Determining interactions and hit types

Since pages that use AJAX typically do not reload, there are multiple interactions a user can take on your site. When implementing Adobe Analytics, make sure that you differentiate page views from link tracking calls. Consider the following question for each interaction a user can take on your site:

*When a user interacts with my site, does that interaction change enough of the content on the page to qualify as a new page?*

* If the answer is **yes**, consider using a page view tracking call (`s.t()`).
* If the answer is **no**, consider tracking that interaction using a link tracking call (`s.tl()`).

>[!NOTE]
>
>Not all interactions or clicks need to be recorded. Carefully consider which actions are most important to track, and send data to Adobe accordingly.

## Clearing variables on each page

Variable values persist on pages using AJAX since the page does not reload. Therefore, special accommodation is required to clear variable values so they do not incorrectly persist across hits. Adobe offers the [`clearVars`](../vars/functions/clearvars.md) function to easily clear out variable values. Make sure that you use this function after sending each hit to Adobe, and before you set variable values for the next hit.

>[!TIP]
>
>The `clearVars()` function is not available in H Code. If you have not upgraded to AppMeasurement, set each Analytics variable value to an empty string.

## Examples

The following example uses simple JavaScript to clear existing variable values, set new values, then send an image request to Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```
