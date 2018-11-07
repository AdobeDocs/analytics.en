---
title: Title of page
---

# Title of page

A report suite is a silo of data that Adobe Analytics uses to pull reports. An organization can have many report suites, each containing different data sets. While separate report suites were important in the past, having a single report suite has become more advantageous. The introduction to virtual report suites and report time processing allows a user to create their own subsets of data, allowing the flexibility to obtain both global and site-specific data.

This article is designed for system-level administrators or analytics admins to prepare for data collection.

## Prerequisites
[Adobe Experience Cloud first admin guide](first-admin-guide.md): Ensure a system-level administrator has granted your user access to Adobe Analytics via the Experience Cloud

## Create a report suite
> Note: There is also a way to create a report suite using the legacy Analytics admin console. Adobe recommends using the report suite setup wizard outlined here.

1. Log in to https://marketing.adobe.com using your Adobe ID credentials.
2. Click the 9-square icon in the upper right, then click the colored Analytics logo.
3. You should see a 'Welcome to Adobe Analytics' modal window automatically pop up. If you don't, click the help icon in the upper right, then select 'Welcome to Adobe Analytics'.
4. In the modal window, click Start Setup.
5. Follow each prompt that outlines the basics like property type, industries, and time zone. Click Next.
6. The report suite is now created. Adobe recommends also having a development report suite, so testing does not taint customer data. Click the help icon in the upper right, then select 'Welcome to Adobe Analytics' again.
7. In the modal window click Start Setup.
8. Name this report suite the same, except append "- DEV" at the end. Since this report suite will only receive internal traffic, the estimated size can be the smallest.
9. Click Next to finish creating your dev report suite.

## Troubleshooting
- After logging in to the Experience Cloud, the Analytics icon is greyed out.
  - This means your account has not been granted the correct permissions to Analytics. Work with a system-level admin in your organization to ensure you belong to a profile with adequate permissions to access Adobe Analytics.
- After logging in to Adobe Analytics, the 'Welcome to Adobe Analytics' popup and dropdown is missing.
  - Ensure that you've logged in through the Experience Cloud, and not through my.omniture.com. Users who log in through my.omniture.com do not have the report suite setup wizard available.

## Next steps
- [Create and configure a property for Adobe Analytics in Launch](analytics-property-launch.md): Create an area to manage your Analytics implementation
