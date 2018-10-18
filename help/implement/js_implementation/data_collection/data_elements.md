---
description: You can capture the values of form elements, such as radio button and checkbox items, into reports. This helps you analyze the most popular choices in your online forms.
keywords: Analytics Implementation
seo-description: You can capture the values of form elements, such as radio button and checkbox items, into reports. This helps you analyze the most popular choices in your online forms.
seo-title: Collect data from form elements
solution: Analytics
title: Collect data from form elements
topic: Developer and implementation
uuid: c3b754e5-3fe2-46cd-b898-6304802643af
index: y
internal: n
snippet: y
---

# Collect data from form elements

You can capture the values of form elements, such as radio button and checkbox items, into reports. This helps you analyze the most popular choices in your online forms.

 For example, if you had a radio button letting the user specify his or her favorite genre of music (such as rock, rap, classical, or jazz), you could capture this response in a variable to determine the overall music preferences of your user base.

The best way to capture this data depends on how your forms are processed. It also depends on whether the form selections you want to capture are available in the query string on the page following the form submission. Examples in this article are given in PHP. However, you can adapt these concepts to another language, depending on your server environment.

This information is suited for advanced users who are well-versed in both reporting and implementation. Do not attempt to make any edits to your implementation without complete knowledge of its consequences. If you require implementation changes, contact your organization's Account Manager.

## GET Method {#section_7A2B35822BFF4F6EB57940B31AE6303A}

If your form uses a [!UICONTROL GET] method to submit data, you have access to the desired data in the query string of the URL on the page following form submission. You can use the [!UICONTROL getQueryParam] plug-in to capture this data out of the query string automatically and place it into the variable of your choosing.

## POST Method {#section_56715C30EF374BA7AA12B946B50E4A9A}

If your form uses a [!UICONTROL POST] method to submit data (which is more common), you have the results for each specific form element available to you in the [!UICONTROL $_POST superglobal]. To capture this in a variable, you want to determine the form element name in question. Using the music genre example mentioned before, part of the form element in question look like this:

```
<input type="radio" name="music_genre" value="rock">
```

This radio button belongs to the "music_genre" form element. You then have access to the user's selected value by using $_POST['music_genre']. This can be written to a variable on the page following the form submission:

```js
s.eVar1="<?=$_POST['music_genre'];?>"
```

The [!UICONTROL eVar1] variable receives a copy of whatever value was submitted to your server through the form, as specified in the value= property.

If you need additional information regarding this custom implementation method, contact your organization's Account Manager. They can arrange a meeting with one of our Implementation Consultants to provide the help you need. 
