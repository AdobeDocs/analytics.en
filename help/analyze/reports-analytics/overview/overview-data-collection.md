---
description: Learn about how data is collected for Adobe Analytics.
subtopic: Get started
title: About Data Collection
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 34a7be55-519a-4e04-95a3-99b0f6e04b3e
---
# About Data Collection

Learn about how data is collected for Adobe Analytics.

Every page Adobe tracks has a small snippet of Adobe-authorized JavaScript code. Your account manager provides this code.

At a high level, the data collection process flows as follows:

![](assets/data_collection.png)

1. A visitor visits a web page that contains the data collection code.
1. As the page loads, data collection code sends an image request (called a web beacon) to Adobe data collection servers. The image request contains the data you want to collect about the visitor's interaction with your website.
1. Adobe stores the data in report suites. You can log in to access report suite data and generate reports related to visitor activity on your website.

Data collection is very quick and does not noticeably affect page load times. Collected data includes page views that result from clicking the browser **Reload** or **Back** buttons. The JavaScript code runs even when the page is retrieved from cache.

See [Data Collection in Analytics.](/help/import/home.md)
