---
title: Comparison of different bot exclusion methods
description: Lets you compare different methods of excluding bots.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
feature: Bot Removal
---
# Comparison of different bot exclusion methods

The following table shows different methods of excluding bots and how they stack up against each other.

| Method | Bot Rules | Exclude by IP Address | Customer Attributes | Segmentation | 3-rd party scoring + Segmentation | Suppress Server Call​​ for Bots at Runtime | Custom DB VISTA rule |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Description of method for excluding data** | ​Exclude based on user-agent, IP address, or IP address range | IP address | ​A flag in customer attributes that identifies ECID as a bot | ​Criteria in an Analytics segment that identifies known bots based on bot behavior | ​A 3rd party such as [Perimeter X](https://www.perimeterx.com) or [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp) assigns each page view a score on how likely it is to be a bot. Score is sent into Analytics and segments can be used to filter data out based on the score. | ​Client-side logic stops the Analytics server call from being executed for bots. | ​A VISTA rule will move traffic from bots that meet certain criteria to a separate report suite. |
| **​Bot names are available for reporting?** | Yes | No | No | No | No | No | Yes |
| **​Able to see which pages are being visited by bots?** | Yes | No | No | No | Yes | No | Yes |
| ​**Incurs server call cost for bots?** | Yes | Yes | Yes | Yes | Yes | No | Yes |
| **Bot data available in data feeds?** | No | No | Yes | Yes | Yes | No | Yes |
| **Able to ​report on bot traffic as if they are actual server calls?** | No | No | Yes | Yes | Yes | No | No |
| **Can retroactively remove data from a data set?** | No | No | ​Yes, once declared IDs are implemented | Yes | Yes, once scores are implemented | No | No |
| **Is subject to Uniques limits in criteria?** | No | No | No | Yes | No | No | No |
| **Is s​ubject to additional cost?** | No | No | ​Possibly, depending on Analytics SKU | No | Yes | No | ​Yes - cost to implement and maintain a VISTA rule |
