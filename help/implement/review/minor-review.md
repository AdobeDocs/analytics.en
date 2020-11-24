---
title: Minor Implementation Review checklist (after each website release)
description: Follow this checklist to ensure that your implementation stays error free and in line with your KPIs.
---

# Minor Implementation Review (after each website release)

Why should you review your implementation after each website release? Because you need to make sure your code updates didn’t have any unintended ramifications, and you should address any issues with data quality while they're still small. If you consistently do this Minor Review after each website release, you’ll find that your [Major Reviews](/help/implement/review/major-review.md) (every 6 months) are much easier. You will also prevent small issues from growing into big data issues that could erode stakeholders’ confidence. 

## 1. How did the release impact the data for that section of the site?	

Do thorough unit testing: Review all the code and variables that correspond to the section of the site you just updated to ensure that the new tracking is working as designed.

## 2. Update your documentation

Update your Business Requirement Document (BRD) and Solution Design Reference (SDR) with any variables you added/changed to accommodate the launch. 

Don’t have documentation of your implementation? Export a list of variables and create your BRD or SDR using [this template](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 3. Start with your top 5 KPIs

Knowing your top 5 key performance indicators (KPIs) will help you determine the associated metrics and dimensions you need to examine. If you haven’t refreshed your KPIs in the last 6 months or if your business hasn’t created KPIs yet, follow [these instructions](/help/implement/review/define-kpis.md). 

## 4. Are all the KPI metrics and variables still functioning well after the release?

Remember, any code updates can have unintended ramifications. You want to make sure that all the metrics and dimensions associated with [your top 5 KPIs](/help/implement/review/define-kpis.md) are still functioning properly. To do this:

* **Create dashboards** to see hourly trended views of these critical metrics and variables 
You can also set up intelligent alerts for each metric) and monitor them for a day or two post-release, to ensure you’re getting the data you expect, and the data is correct. Look for inflection points. Be prepared to remediate any critical issues immediately. If you find any discrepancies that don’t look correct, look in your data layer, tag manager rules, and processing rules to find out why.
* **Re-run the Analytics Health Dashboard** to monitor broad trends of your KPI metrics and variables.
For more details about how to make sure your metrics and variables are functioning properly, read these tips from Adobe Analytics Champion Sarah Owen.

## Are there gaps in your data quality?

Assess the situation and make a plan to remediate the data. Then make the needed changes, update your documentation, and inform your stakeholders about the changes you made.

Watch this video from Adobe Analytics Champion Sarah Owen about natural times when you can fit reviews of your implementation into your busy schedule:

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
