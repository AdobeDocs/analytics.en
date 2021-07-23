---
title: AppMeasurement for JavaScript
description: Learn how to implement Adobe Analytics using JavaScript without a tag management system.
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
---
# AppMeasurement for JavaScript

AppMeasurement for JavaScript has historically been a common method to implement Adobe Analytics. However, with increasing popularity of Tag Management Systems, using [tags in Adobe Experience Platform](../launch/overview.md) is recommended.

## Overall workflow sending data to Adobe using JavaScript

1. Load the `AppMeasurement.js` file. This file contains the libraries required to send data to Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Define configuration variables within `AppMeasurement.js`. When the Analytics object is instantiated, these variables make sure data collection settings are correct. See [Configuration variables](../vars/config-vars/configuration-variables.md) for a full list of variables you can define.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Define page-level variables within your site's page code. These variables determine specific dimension and metrics sent to Adobe. See [Page variables](../vars/page-vars/page-variables.md) for a full list of variables you can define.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. When all page-level variables are defined, send the data to Adobe using the `t()` method. See [t](../vars/functions/t-method.md) for more information.

   ```js
   s.t();
   ```
