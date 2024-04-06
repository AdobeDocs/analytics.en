---
title: Migrate from AppMeasurement to the Web SDK
description: Update your Adobe Analytics implementation from the AppMeasurement JavaScript library to the Web SDK JavaScript library.
---
# Migrate from AppMeasurement to the Web SDK

This implementation path involves a methodical migration approach to move from an AppMeasurement implementation to a Web SDK JavaScript library implementation. Other implementation paths are covered on separate pages:

* [Analytics extension to Web SDK extension](analytics-extension-to-web-sdk.md): Take a smooth and methodical approach to move from the Adobe Analytics tag extension in Adobe Experience Platform Data Collection to the Web SDK tag extension. This approach suppresses the need to use XDM until your organization is ready to use Adobe Experience Platform services, such as Customer Journey Analytics. Use the `data` object instead of the `xdm` object to send data to Adobe.
* [Web SDK JavaScript library](web-sdk-javascript-library.md): A fresh Web SDK installation using the Web SDK JavaScript library (`alloy.js`). Manage the implementation yourself instead of using the tags UI. Requires the Adobe Analytics ExperienceEvent field group, which includes typical Analytics variables to be included in your XDM schema.
* [Web SDK tag extension](web-sdk-tag-extension.md): A fresh Web SDK installation where you manage the implementation using tags in Adobe Experience Platform Data Collection. Requires the Adobe Analytics ExperienceEvent field group, which includes typical Analytics variables to be included in your XDM schema.

## Advantages and disadvantages of this implementation path

Using this migration approach has both advantages and disadvantages. Carefully weigh each option to decide which approach is best for your organization.

| Advantages | Disadvantages |
| --- | --- |
| <ul><li>**Uses your existing implementation**: This approach does not require a net-new implementation. You can use your existing data layer and code with minimal changes.</li><li>**Does not require a schema**: While a schema is required to ultimately send data to Customer Journey Analytics, a schema is not required for this stage of migration to the Web SDK. Instead, you can populate the `data` object, which sends data straight to Adobe Analytics. Once migration to the Web SDK is complete, then you can create a schema for your organization and use datastream mapping to populate applicable XDM fields.</li></ul> | <ul><li>**Implementation changes require developer intervention**: If you want to make changes to your Web SDK implementation, you must work with your development team to edit the code on your site. The approach that [migrates to the Web SDK tag extension](analytics-extension-to-web-sdk.md) avoids this disadvantage.</li><li>**Implementation technical debt**: Since this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes when needed.</li><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the `data` object be an entry in the datastream mapping tool that assigns it to an XDM schema field. While this mapping workflow only needs to be done once and doesn't require implementation changes, it is a required action that is not needed when sending data directly to XDM.</li></ul> |


use cases

update s object to data.__adobe.analytics

change function calls to sendEvent calls
