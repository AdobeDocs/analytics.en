---
description: File downloads and exit links can be automatically tracked based on parameters set in the AppMeasurement for JavaScript file.
keywords: Analytics Implementation
subtopic: Link tracking
title: The s.tl() Function - Link Tracking
topic: Developer and implementation
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
---

# The s.tl() Function - Link Tracking

If your organization prefers to have more control over the links to track and their behavior, manual link tracking is recommended. Use the `s.tl()` function to manually send link tracking image requests with the exact content desired. If basic link tracking is all that is needed, see `s.trackDownloadLinks` and `s.trackExternalLinks` under [Configuration variables](c-variables/configuration-variables.md). Custom links cannot automatically be tracked.

> [!NOTE] Link tracking code is often very specific to your site and reporting needs. Adobe recommends prior implementation experience or an implementation consultant to understand how to use this feature based on your business needs.

## Syntax and examples

Basic syntax:

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

Basic examples:

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

> [!NOTE] The first argument to this function is either the JavaScript variable `this` or boolean `true`. The second and third arguments to this function are both strings. Make sure you use string quotes correctly when using this function.

### this/true (required)

The first argument determines if the browser waits up to 500ms before navigating away from the page. If an image request is sent sooner than 500ms, the page immediately navigates to the clicked link.

* `this`: Wait up to 500ms to give AppMeasurement time to send an image request. Default value.
* `true`: Do not wait. If the link navigates away from the page, it is possible an image request is not sent.

The delay is only necessary when a link leaves the page.

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (required)

The second argument has three valid values depending on the type of link that you want to capture. It determines which dimension in Adobe Analytics the image request populates.

* `d`: File Downloads
* `e`: Exit Links
* `o`: Custom links

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName (required)

This argument can be any custom value up to 100 bytes. It determines the dimension value in reporting.

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides (optional)

Lets you change variable values for a single call. If you use the doneAction argument and have no variable overrides, use `null`.

### doneAction (optional)

Specifies a navigation action to execute after the track link call completes. Requires the use of `s.useForcedLinkTracking` and `s.forcedLinkTrackingTimeout`. The doneAction variable can be the string `navigate`, which causes the method to set `document.location` to the href attribute of `linkObject`. The doneAction variable can also be a function allowing for advanced customization.

If providing a value for doneAction in an anchor `onClick` event, you must return `false` after the `s.tl` call to prevent the default browser navigation.
To mirror the default behavior and follow the URL specified by the href attribute, provide a string of `navigate` as the doneAction. Optionally, you can provide your own function to handle the navigation event by passing this function as the doneAction.

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## Using JavaScript functions with link tracking

You can consolidate link tracking code into a self-contained JavaScript function defined on the page or in a linked JavaScript file. Calls can then be made in the onClick function of each link.

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## Avoiding Duplicate Link Counts {#section_9C3F73DE758F4727943439DED110543C}

It is possible for links to double count in situations where the link is normally captured by automatic file download or exit link tracking. For example, if you are tracking PDF downloads automatically, an `s.tl` call results in a duplicate download count:

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

To ensure link double counting does not occur, use the following modified JavaScript function:

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
