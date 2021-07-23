---
title: Migrating to AppMeasurement for JavaScript
description: Determine what's needed to migrate your implementation off of H Code.
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
---
# Migrating to AppMeasurement for JavaScript

If your implementation still uses H Code, Adobe highly recommends migrating to the latest version of AppMeasurement. Implementing Analytics through [tags in Adobe Experience Platform](../launch/overview.md) is recommended, however an updated JavaScript implementation can be used.

The following notable changes are present in AppMeasurement when compared to H Code:

* 3-7x faster than H Code.
* Lighter than H Code - 21kb uncompressed vs. H Code, which is is 33kb uncompressed.
* The library and page code can be deployed inside the `<head>` tag.
* Existing page-level H Code is compatible with AppMeasurement.
* The library provides native utilities to get query parameters, read and write cookies, and perform advanced link tracking.
* The library does not support dynamic account configuration variables (including `dynamicAccountSelection`, `dynamicAccountMatch`, and `dynamicAccountList`).

The following steps outline a typical migration workflow.

1. **Download the new AppMeasurement file**: Access the new file by logging in to Adobe Analytics, then navigating to Admin > All admin > Code manager. The downloaded compressed file contains a minified `AppMeasurement.js` file, along with Media and Integrate modules.
1. **Copy your `s_code.js` customizations to `AppMeasurement.js`**: Move all the code before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in `s_code.js` to the beginning of `AppMeasurement.js`.
1. **Update all plug-ins**: Make sure you are using the latest version of each plug-in listed in your `s_code.js` file. This includes the Media and Integrate modules.
1. **Deploy the AppMeasurement.js file**: Upload your `AppMeasurement.js` file to your web server.
1. **Update script references to point to `AppMeasurement.js`**: Make sure all pages reference `AppMeasurement.js` instead of `s_code.js`.

## Example Appmeasurement code

A typical `AppMeasurement.js` file. Make sure that configuration variables are set above the `doPlugins` function.

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.data.adobedc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */

```

## Example page code

Typical code that loads on each page.

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

Make sure that you have also included a reference to `AppMeasurement.js` and `VisitorAPI.js` on each page. See [JavaScript Implementation](/help/implement/js/overview.md) for more information.
