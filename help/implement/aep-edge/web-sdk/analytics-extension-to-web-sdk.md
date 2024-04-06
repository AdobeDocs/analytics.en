---
title: Migrate from the Adobe Analytics tag extension to the Web SDK tag extension
description: Update your Analytics implementation on Adobe Experience Platform Data Collection tags to use the Web SDK extension.
---
# Migrate from the Adobe Analytics tag extension to the Web SDK tag extension

This implementation path involves a methodical migration approach to move from the Adobe Analytics tag extension to the Web SDK tag extension. Other implementation paths are covered on separate pages:

* [AppMeasurement to Web SDK JavaScript library](appmeasurement-to-web-sdk.md): A smooth and methodical approach to migrate to the Web SDK, except it does not use tags. Instead, you manually remove the Adobe Analytics data collection library (`AppMeasurement.js`) and replace it with the Web SDK JavaScript library (`alloy.js`).
* [Web SDK tag extension](web-sdk-tag-extension.md): A fresh Web SDK installation where you manage the implementation using tags in Adobe Experience Platform Data Collection. Requires the Adobe Analytics ExperienceEvent field group, which includes typical Analytics variables to be included in your XDM schema.
* [Web SDK JavaScript library](web-sdk-javascript-library.md): A fresh Web SDK installation using the Web SDK JavaScript library (`alloy.js`). Manage the implementation yourself instead of using the tags UI. Requires the Adobe Analytics ExperienceEvent field group, which includes typical Analytics variables to be included in your XDM schema.

## Advantages and disadvantages of this implementation path

Using this migration approach has both advantages and disadvantages. Carefully weigh each option to decide which approach is best for your organization.

| Advantages | Disadvantages |
| --- | --- |
| <ul><li>**No code changes on your site**: Since your implementation already has tags installed, all migration updates can be made in the tags interface.</li><li>**Uses your existing implementation**: This approach does not require a net-new implementation. While it does require new rule actions, you can reuse your existing data elements and rule conditions with minimal changes.</li><li>**Does not require a schema**: While a schema is required to ultimately send data to Customer Journey Analytics, a schema is not required for this stage of migration to the Web SDK. Instead, you can populate the `data` object, which sends data straight to Adobe Analytics. Once migration to the Web SDK is complete, then you can create a schema for your organization and use datastream mapping to populate applicable XDM fields.</li></ul> | <ul><li>**Implementation technical debt**: Since this approach uses a modified form of your existing implementation, it can be harder to track implementation logic and perform changes when needed. Custom code can be particularly difficult to debug.</li><li>**Requires mapping to send data to Platform**: When your organization is ready to use Customer Journey Analytics, you must send data to a data set in Adobe Experience Platform. This action requires that every field in the `data` object be an entry in the datastream mapping tool that assigns it to an XDM schema field. While this mapping workflow only needs to be done once and doesn't require implementation changes, it is a required action that is not needed when sending data directly to XDM.</li></ul> |



use cases - still send data to adobe analytics

update rules

publish updates

disable analytics extension
