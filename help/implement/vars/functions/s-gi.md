---
title: s_gi()
description: Create and track instances of AppMeasurement.
---

# s_gi

The `s_gi()` function instantiates or finds an instance of AppMeasurement by report suite ID. AppMeasurement keeps track of every instance created, and `s_gi()` returns the existing instance for a report suite if one exists. If an instance does not exist, a new instance is created.

## s_gi() in Adobe Experience Platform Launch

The Analytics extension instantiates and manages the tracking object for you. However, you can also set a global tracking object in the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Library Management] accordion, and select any radio button other than [!UICONTROL Manage the library for me].

The global variable text field lets you set a custom tracking object. Its default value is `s`.

## s_gi() in AppMeasurement and Launch custom code editor

Call the `s_gi()` function to instantiate a tracking object. Its only argument contains a comma-delimited string of report suite IDs. The report suite ID argument is required.

> [!TIP] Adobe recommends using the `s` variable as a tracking object. Adobe uses `s` in its documentation, implementation examples, and plug-ins. However, you can use any variable as long as you are consistent across your site.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

> [!WARNING] The following sections and examples contain complex implementation topics. Thoroughly test your implementation and track important customizations in your organization's [solution design document](../../prepare/solution-design.md).

## Manage multiple implementations using different tracking objects

You can send different data to different report suites if you instantiate multiple tracking objects. These two tracking objects operate independently of each other.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Restore AppMeasurement variables after overwriting the s object

Some 3rd-party tools might also use the JavaScript `s` object. If you accidentally overwrite the `s` object on your site, you can call `s_gi` with the same RSID string argument to restore all overwritten variables and methods.

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## Reference the same tracking object with multiple variables

If two variables reference the same `s_gi()` function with the same report suite, you can use the variables interchangeably.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
