---
title: Implement Adobe Analytics using the Adobe Experience Platform Web SDK
description: Use the Web SDK extension in Adobe Experience Platform Data Collection to send data to Adobe Analytics.
---
# Implement Adobe Analytics using the Adobe Experience Platform Web SDK

You can use the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) to send data to Adobe Analytics. This implementation method works by translating the [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) into a format used by Analytics.

You can send data to Experience Edge directly using the Web SDK, or through the Web SDK extension in Tags.

## Web SDK

A high-level overview of the implementation tasks:

![Implement Adobe Analytics using Web SDK workflow](../../assets/websdk-annotated.png)

| | Task | More Information | 
|-| ------|------------------|
| 1 | Ensure you have **defined a report suite**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) |
| 2 | **Setup schemas and datasets**. To standardize data collection for use across applications that leverage Adobe Experience Platform, Adobe has created the open and publicly documented standard, Experience Data Model (XDM). | [Schemas UI overview](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) and [Datasets UI overview](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en) |
| 3 | **Create a data layer** to manage the tracking of the data on your website. | [Create a data layer](../../prepare/data-layer.md) |
| 4 | **Install the prebuilt standalone version**. You can reference the library (`alloy.js`) on the CDN directly on your page or download and host it on your own infrastructure. Alternatively, you can use the NPM package. | [Installing the prebuilt standalone version](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) and [Using the NPM package](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)|
| 5 | **Configure a datastream**. A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web SDK. | [Configure a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) |
| 6 | **Add an Adobe Analytics service** to your datastream. That service controls whether and how data is sent to Adobe Analytics. | [Add Adobe Analytics service to a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics)
| 7 | **Configure the Web SDK**. Ensure the library that you installed in step 4 is properly configured with the datastream ID (formerly known as edge configuration id (`edgeConfigId`)), organization id (`orgId`), and other available options. | [Configure the Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) | 
| 8 | **Execute commands** and/or **track events**. After the base code has been implemented on your webpage, you can begin executing commands and tracking events with the SDK. | [Execute commands](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) and [Track events](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) |
| 9 | **Extend and validate your implementation** before pushing it out to production. | | 



## Web SDK extension

A high-level overview of the implementation tasks:

![Implement Adobe Analytics using Web SDK extension workflow](../../assets/websdk-extension-annotated.png)

| | Task | More Information | 
|-| ------|------------------|
| 1 | Ensure you have **defined a report suite**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) |
| 2 | **Setup schemas and datasets**. To standardize data collection for use across applications that leverage Adobe Experience Platform, Adobe has created the open and publicly documented standard, Experience Data Model (XDM). | [Schemas UI overview](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) and [Datasets UI overview](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en) |
| 3 | **Create a data layer** to manage the tracking of the data on your website. | [Create a data layer](../../prepare/data-layer.md) |
| 4 | **Configure a datastream**. A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web SDK. | [Configure a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) |
| 5 | **Add an Adobe Analytics service** to your datastream. That service controls whether and how data is sent to Adobe Analytics. | [Add Adobe Analytics service to a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics)
| 6 | **Create a tag property**. Properties are overarching containers used to reference tag management data.| [Create or configure a tag property for web](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) |
| 7 | **Install and configure the Web SDK extension** in your tag property. Configure the Web SDK extension to send data to the datastream configured in step 4. | [Adobe Experience Platform Web SDK extension overview](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) |
| 8 | **Iterate, validate, and publish** to production. Add the tag property to your web site. Then use data elements, rules, and so on, to customize your implementation. | [Publishing overview](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en)



## Additional resources

Tags can be highly customized. Learn more about how you can get the most out of Adobe Analytics by including the right data in your implementation.

-   [Tags documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): Learn how the interface works and what extensions are available.

-   [Adobe Experience Platform Web SDK documentation](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en)
