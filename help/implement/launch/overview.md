---
title: Implement Adobe Analytics with tags in Adobe Experience Platform
description: Learn how to implement Adobe Analytics using tags
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
---
# Implement Adobe Analytics with tags in Adobe Experience Platform

Through the lifetime of Adobe Analytics, Adobe has offered several different methods to implement code on your site for data collection. Adobe's current recommend method is through tags in Adobe Experience Platform.

Tags in Adobe Experience Platform is a tag management solution that lets you deploy Analytics code alongside other tagging requirements. Adobe offers integrations with other solutions and products, and lets you deploy custom code. All of these tasks can be done without relying on any development teams in your organization to update code on your site.

All customers with an active Adobe Experience Cloud contract can use tags. If you are not sure if you have access, contact one of your organization's Experience Cloud system admins.

## Overall workflow

Getting an implementation running using tags follows these steps:

1. **Gain access to tags**: You can obtain access to Platform tags through a system admin in your organization.
2. **Create a tag property**: Properties are overarching containers used to reference tag management data.
3. **Deploy to a development environment**: Have an environment where you can iterate on the development of tags.
4. **Validate and publish to production**: Make sure everything is working, then publish it live.

See [Create an Analytics tag property](create-analytics-property.md) to get started.

## Additional resources

Tags can be highly customized. Learn more about how you can get the most out of Adobe Analytics by including the right data in your implementation.

* [Tags documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): Learn how the interface works and what extensions are available.
* [Adobe Analytics extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html): Use the Analytics extension to send data to Adobe Analytics.
* [Implementation variables](../vars/overview.md): Determine what variables you want to send to data collection servers.
