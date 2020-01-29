---
title: getValOnce
description: Prevents AppMeasurement from setting a variable to the previously defined value.
---

# getValOnce

The `getValOnce` plug-in prevents a variable from being set to the previously defined value. It uses a cookie to determine a variable's last seen value. If the current value matches the cookie value, the variable is overwritten with a blank string. This plug-in is useful to prevent inflation on metrics like 'Occurrences' when visitors refresh the page or click the Back button.

When you use this method, AppMeasurement compares the currently defined value to what is stored in a cookie. If the defined value is different from the cookie value, the plug-in returns the existing value without any changes. If the defined value is the same as the cookie value, the plug-in returns an empty string.

This plug-in only checks the last defined value. It prevents the same value from being set multiple times consecutively. It does not check beyond the previous value. You can swap back and forth between two values without the plug-in emptying the string.

## Install the getValOnce plug-in using Adobe Experience Platform Launch

You can install the `getValOnce()` plug-in when configuring the Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Configure tracking using custom code] accordion, which reveals the [!UICONTROL Open Editor] button.

Open the custom code editor and paste the plug-in code provided below. Once installed, you can use the `getValOnce()` function in the custom code editor of rules to assign variable values.

## Install the getValOnce plug-in using AppMeasurement

You can install the `getValOnce()` plug-in by editing `AppMeasurement.js`:

1. Download and open the `AppMeasurement.js` file located on your web server.
2. Paste the plug-in code provided below anywhere after the tracking object is instantiated (using [`s_gi`](../functions/s-gi.md)).
3. Save the JS file and upload the new version to your web server.

Once installed, you can use the `getValOnce()` method to assign variable values.

## Plug-in code

```js
// getValOnce v1.2
s.getValOnce = function(v,c,e,t) {var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?60000:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e==0?0:a);}return v==k?'':v};
```

## Use the getValOnce plug-in with AppMeasurement and Launch custom code editor

The `getValOnce` returns a string either containing the already set value or an empty string. Use this plug-in after you set the variable value on the page. It uses the following arguments:

* **Variable**: The variable to check. This argument is typically the same as the variable being defined.
* **Cookie**: The name of the cookie to store the previous value. You can use any cookie name you want, however Adobe recommends including the prefix `gvo_` to easily identify the purpose of this cookie.
* **Expiration** (Optional): The number of days until the cookie expires. The cookie expires at the end of the browser session by default.
* **Minute flag** (Optional): If you set this argument to the string value `"m"`, the expiration argument uses minutes instead of days.

```js
// If this is the first page of the visitor, the output is "Example value". If you refresh the page, the output is an empty string.
s.eVar1 = "Example value";
s.eVar1 = s.getValOnce(s.eVar1,"gvo_v1");

// Keep the previous value for up to 15 days
s.eVar1 = "Example value";
s.eVar1 = s.getValOnce(s.eVar1,"gvo_v1",15);

// Keep the previous value for up to 15 minutes
s.eVar1 = "Example value";
s.eVar1 = s.getValOnce(s.eVar1,"gvo_v1",15,"m");
```

> [!TIP] If using Launch, initially define your variable values in rules as you normally would. You can then use the `getValOnce` plug-in on each desired variable in the `doPlugins` function to validate those variable values.
