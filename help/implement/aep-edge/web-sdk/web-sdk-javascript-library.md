---
title: Send data to Adobe Analytics using the Web SDK JavaScript library
description: Start with a clean Web SDK implementation to send data to Adobe Analytics using the JavaScript library.
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
---
# Send data to Adobe Analytics using the Web SDK JavaScript library

This implementation path involves a fresh Web SDK installation using the Web SDK JavaScript library. Other implementation paths are covered on separate pages:

* [Web SDK tag extension](web-sdk-tag-extension.md): A fresh Web SDK installation using the Web SDK tag extension. Similar to the Web SDK JavaScript library approach (this page), except you manage the implementation using tags in Adobe Experience Platform Data Collection. It requires the Adobe Analytics ExperienceEvent field group, which includes typical Analytics variables to be included in your XDM schema.
* [Analytics extension to Web SDK extension](analytics-extension-to-web-sdk.md): Take a smooth and methodical approach to move from the Adobe Analytics tag extension to the Web SDK tag extension. This approach suppresses the need to use XDM until your organization is ready to use Adobe Experience Platform services, such as Customer Journey Analytics. Use the `data` object instead of the `xdm` object to send data to Adobe.
* [AppMeasurement to Web SDK JavaScript library](appmeasurement-to-web-sdk.md): A smooth and methodical approach to migrate to the Web SDK, except it does not use tags. Instead, you can manually remove the Adobe Analytics data collection library (`AppMeasurement.js`) and replace it with the Web SDK JavaScript library (`alloy.js`).

## Advantages and disadvantages of this implementation path

Using the Web SDK JavaScript library to send data to Adobe Analytics has both advantages and disadvantages. Carefully weigh each option to decide which approach is best for your organization.

| Advantages | Disadvantages |
| --- | --- |
| <ul><li>**Direct approach**: This implementation path is more straightforward than approaches that move existing Adobe Analytics implementations. If you do not have a current Adobe Analytics implementation to worry about, populate the applicable Web SDK XDM fields.</li><li>**Predefined schema**: If your organization does not have a need for your own schema, you can simply use the schema geared towards Adobe Analytics. This concept applies even as you move towards Customer Journey Analytics; the concept of props and eVars don't apply to Customer Journey Analytics, but you can continue using props and eVars as simple custom dimensions.</li></ul> | <ul><li>**Implementation changes require developer intervention**: If you want to make changes to your Web SDK implementation, you must work with your development team to edit the code on your site. The approach that uses the [Web SDK tag extension](web-sdk-tag-extension.md) avoids this disadvantage.</li><li>**Locked into using a specific schema**: When your organization moves to Customer Journey Analytics, you must choose to continue using the Adobe Analytics schema, or migrate to your own organization's schema (which would be a separate data set). If your organization wants to avoid both the Adobe Analytics schema and migration to a separate data set when moving to Customer Journey Analytics, Adobe recommends one of the following two methods:</li><ul><li>Use the `data` object: The `data` object allows you to send data to Adobe Analytics without conforming to an XDM schema. Once your organization's schema is created, you can use datastream mapping to map `data` object fields to XDM. Both the [Analytics extension to Web SDK extension](analytics-extension-to-web-sdk.md) and [AppMeasurement to Web SDK JavaScript library](appmeasurement-to-web-sdk.md) use this `data` object.</li><li>Skip Adobe Analytics entirely: If you are implementing the Web SDK, you can send that data to a dataset in Adobe Experience Platform for use in Customer Journey Analytics. You can use any schema that you like; Adobe Analytics is not involved at all in this workflow, and therefore does not require the Adobe Analytics ExperienceEvent field group. This method incurs the least amount of technical debt, but also leaves Adobe Analytics out of the picture entirely.</li></ul></ul> |

>[!IMPORTANT]
>
>This implementation method requires that you use a schema configured for Adobe Analytics. If your organization plans to use your own schema with Customer Journey Analytics in the future, use of the Adobe Analytics schema can create confusion for data admins or architects. There are several options to mitigate this obstacle:
>
>* You can use the Adobe Analytics schema in CJA. Note that CJA does not have a concept of props or eVars; they are treated as any other schema field. Also note that the use of the Adobe Analytics schema in CJA can make it more difficult to use other platform services, such as Adobe Journey Optimizer or Real-Time Customer Data Platform.
>* You can use the data object, similar to a migration workflow. Note that the use of the data object requires that you map each data object field to an XDM schema field.
>* You can skip the Adobe Analytics implementation entirely, and send data to Adobe Experience Platform using your own schema. This approach is ideal long-term, and allows your organization to start using Customer Journey Analytics.

## Steps required to implement the Web SDK JavaScript library

A high-level overview of the implementation tasks:

![How to implement Adobe Analytics using Web SDK workflow, as described in this section.](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Task</b></th><th style="width:35%"><b>More Information</b></th>
</tr>

<tr>
<td>1</td>
<td>Ensure you have <b>defined a report suite</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Setup schemas</b>. To standardize data collection for use across applications that leverage Adobe Experience Platform, Adobe has created the open and publicly documented standard, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html">Schemas UI overview</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Create a data layer</b> to manage the tracking of the data on your website.</td>
<td><a href="../../prepare/data-layer.md">Create a data layer</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Install the prebuilt standalone version</b>. You can reference the library (<code>alloy.js</code>) on the CDN directly on your page or download and host it on your own infrastructure. Alternatively, you can use the NPM package.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html">Installing the prebuilt standalone version</a> and <a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html">Using the NPM package</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configure a datastream</b>. A datastream represents the server-side configuration when implementing the Adobe Experience Platform Web SDK.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html">Configure a datastream<a></td> 
</tr>

<td>6</td>
<td><b>Add an Adobe Analytics service</b> to your datastream. That service controls whether and how data is sent to Adobe Analytics and to which report suite(s) specifically.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Add Adobe Analytics service to a datastream</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configure the Web SDK</b>. Ensure the library that you installed in step 4 is properly configured with the datastream ID (formerly known as edge configuration id (<code>datastreamId</code>)), organization id (<code>orgId</code>), and other available options. Ensure proper mapping of variables. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">Configure the Web SDK</a><br/><a href="../xdm-var-mapping.md">XDM object variable mapping</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Execute commands</b> and/or <b>track events</b>. After the base code has been implemented on your webpage, you can begin executing commands and tracking events with the SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html">Send events</a></td>
</tr>

<tr>
<td>9</td><td><b>Extend and validate your implementation</b> before pushing it out to production.</td><td></td> 
</tr>
</table>
