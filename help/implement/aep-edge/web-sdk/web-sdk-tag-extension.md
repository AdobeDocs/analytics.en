---
title: Send data to Adobe Analytics using the Web SDK tag extension
description: Start with a clean implementation of Adobe Experience Platform Data Collection to send data to Adobe Analytics using XDM and the Adobe Analytics ExperienceEvent field group.
hide: yes
hidefromtoc: yes
---
# Send data to Adobe Analytics using the Web SDK tag extension

This implementation path involves a fresh Web SDK installation using tags in Adobe Experience Platform Data Collection. Other implementation paths are covered on separate pages:

* [Web SDK JavaScript library](web-sdk-javascript-library.md): A fresh Web SDK installation using the Web SDK JavaScript library (`alloy.js`). Similar to the Web SDK tag extension approach (this page), except you manage the implementation yourself instead of using the tags UI. It requires the Adobe Analytics ExperienceEvent field group, which includes typical Analytics variables to be included in your XDM schema.
* [Analytics extension to Web SDK extension](analytics-extension-to-web-sdk.md): Take a smooth and methodical approach to move from the Adobe Analytics tag extension to the Web SDK tag extension. This approach suppresses the need to use XDM until your organization is ready to use Adobe Experience Platform services, such as Customer Journey Analytics. Use the `data` object instead of the `xdm` object to send data to Adobe.
* [AppMeasurement to Web SDK JavaScript library](appmeasurement-to-web-sdk.md): A smooth and methodical approach to migrate to the Web SDK, except it does not use tags. Instead, you manually remove the Adobe Analytics data collection library (`AppMeasurement.js`) and replace it with the Web SDK JavaScript library (`alloy.js`).

## Advantages and disadvantages of this implementation path

Using the Web SDK extension to send data to Adobe Analytics has both advantages and disadvantages. Carefully weigh each option to decide which approach is best for your organization.

| Advantages | Disadvantages |
| --- | --- |
| <ul><li>**Most direct approach**: This implementation path is the most straightforward and typically the recommended path for new Web SDK implementations. If you do not have a current Adobe Analytics implementation to worry about, populate the applicable Web SDK XDM fields.</li><li>**Predefined schema**: If your organization does not have a need for your own schema, you can simply use the schema geared towards Adobe Analytics. This concept applies even as you move towards Customer Journey Analytics; the concept of props and eVars don't apply to Customer Journey Analytics, but you can continue using props and eVars as simple custom dimensions.</li><li>**Manage tags without developer intervention**: Tags allow you to manage your implementation without requesting that developers make code changes to your implementation. Your developers install the tag loader script, and you have full control over how data is collected.</li></ul> | <ul><li>**Locked into using a specific schema**: When your organization moves to Customer Journey Analytics, you must choose to continue using the Adobe Analytics schema, or migrate to your own organization's schema (which would be a separate data set). If your organization wants to avoid both the Adobe Analytics schema and migration to a separate data set when moving to Customer Journey Analytics, Adobe recommends one of the following two methods:<ul><li>Use the `data` object: The `data` object allows you to send data to Adobe Analytics without conforming to an XDM schema. Once your organization's schema is created, you can use datastream mapping to map `data` object fields to XDM. Both the [Analytics extension to Web SDK extension](analytics-extension-to-web-sdk.md) and [AppMeasurement to Web SDK JavaScript library](appmeasurement-to-web-sdk.md) use this `data` object.</li><li>Skip Adobe Analytics entirely: If you are implementing the Web SDK, you can send that data to a dataset in Adobe Experience Platform for use in Customer Journey Analytics. You can use any schema that you like; Adobe Analytics is not involved at all in this workflow, and therefore does not require the Adobe Analytics ExperienceEvent field group. This method incurs the least amount of technical debt, but also leaves Adobe Analytics out of the picture entirely.</li></ul></ul> |


