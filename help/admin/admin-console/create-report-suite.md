---
title: Create a report suite
description: Create a basic container for data collection in Adobe Analytics.
---

# Create a report suite

A report suite is a silo of data that Adobe Analytics uses to pull reports. An organization can have many report suites, each containing different data sets. While separate report suites were important in the past, having a single report suite has become more advantageous. The introduction to virtual report suites and report time processing allows a user to create their own subsets of data, allowing the flexibility to obtain both global and site-specific data.

This article is designed for system-level administrators or analytics admins to prepare for data collection.

## Prerequisites

[Adobe Analytics First Admin Guide](first-admin-guide.md): Ensure a system-level administrator has granted you access to Adobe Analytics via the Experience Cloud Admin Console

## Create a report suite

> [!NOTE] There is also a way to create a report suite in Adobe Analytics using the legacy admin. Adobe recommends using the report suite setup wizard outlined here.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Click the 9-square icon in the upper right, then click the colored Analytics logo.
1. You should see a 'Welcome to Adobe Analytics' modal window automatically pop up. If you don't, click the help icon in the upper right, then select 'Welcome to Adobe Analytics'.
1. In the modal window, click Start Setup.
1. Follow each prompt that outlines the basics like property type, industries, and time zone. Click Next.
1. The report suite is now created. Adobe recommends also having a development report suite, so testing does not taint customer data. Click the help icon in the upper right, then select 'Welcome to Adobe Analytics' again.
1. In the modal window click Start Setup.
Name this report suite the same, except append "- DEV" at the end. Since this report suite will only receive internal traffic, the estimated size can be the smallest.
1. Click Next to finish creating your dev report suite.

For more information on the steps in this modal window, see [Implementation modal](/help/implement/prepare/implementation-modal.md) in the Implement user guide.

## Troubleshooting

**After logging in to the Experience Cloud, the Analytics icon is greyed out.**

This means that your account has not been granted the correct permissions to Analytics. Work with a system-level admin in your organization to ensure you belong to a profile with adequate permissions to access Adobe Analytics.

**After logging in to Adobe Analytics, the 'Welcome to Adobe Analytics' popup and dropdown is missing.**

Ensure that you've logged in through the Experience Cloud, and not through my.omniture.com. User who log in through my.omniture.com do not have the report suite setup wizard available.

## Next steps

[Create and configure a property for Adobe Analytics in Launch](/help/implement/implement-with-launch/create-analytics-property.md): Create an area to manage your Analytics implementation
