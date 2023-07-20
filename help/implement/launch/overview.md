---
title: Implement Adobe Analytics using the Analytics extension
description: Learn how to implement Adobe Analytics using tags and Analytics extension
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
---
# Implement Adobe Analytics using the Analytics extension

Through the lifetime of Adobe Analytics, Adobe has offered several different methods to implement code on your site for data collection. Adobe's current recommended method is through tags in Adobe Experience Platform.

Tags in Adobe Experience Platform is a tag management solution that lets you deploy Analytics code alongside other tagging requirements. Adobe offers integrations with other solutions and products, and lets you deploy custom code. All of these tasks can be done without relying on any development teams in your organization to update code on your site.

All customers with an active Adobe Experience Cloud contract can use tags. If you are not sure if you have access, contact one of your organization's Experience Cloud system admins.

A high-level overview of the implementation tasks:



![How to implement Adobe Analytics using the Analytics extension workflow, as described in this section.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Task</b></th><th style="width:35%"><b>More Information</b></th>
</tr>

<tr>
<td> 1</td>
<td>Ensure you have <b>defined a report suite</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Create a data layer</b> to manage the tracking of the data on your website.</td>
<td>
<a href="../prepare/data-layer.md">Create a data layer</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Create a tag property</b>. Properties are overarching containers used to reference tag management data.</td>
<td><a ref="../launch/create-analytics-property.md">Create an Adobe Analytics tag property</a></td>
</tr>

<tr>
<td>4</td><td><b>Install the Analytics extension</b> in the tag property. Configure the Analytics extension to send data to Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en">Adobe Analytics extension overview</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Deploy to a development environment</b>. Have an environment where you can iterate on the development of tags.</td>
<td><a href="./deploy-dev.md">Deploy an Analytics implementation to a development environment</td>
</tr>

<tr>
<td>6</td> 
<td><b>Validate and publish to production</b>. Add the tag property to your web site. Then use data elements, rules, and so on, to customize your implementation.</td>
<td><a href="./validate-publish-prod.md">Validate a development implementation and publish to production</a></td>
</tr>

</table>

## Additional resources

Tags can be highly customized. Learn more about how you can get the most out of Adobe Analytics by including the right data in your implementation.

- [Tags documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): Learn how the interface works and what extensions are available.

- [Implementation variables](../vars/overview.md): Determine what variables you want to send to data collection servers.
