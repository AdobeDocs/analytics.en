---
title: Focused Review (after each website release)
description: Follow these steps to ensure that your implementation stays error free and in line with your KPIs.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
---
# Focused Review (after each website release)

Why should you review your implementation every few months? So you can address any issues with data quality while they're still small. If you consistently do this Focused Review after each website release, you’ll find that your bi-annual [Full Reviews](/help/implement/review/full-review.md) are much easier. You will also prevent small issues from growing into big data issues that could erode stakeholders’ confidence. 

## 1. Start with your top 5 KPIs

Knowing your top 5 key performance indicators (KPIs) will help you determine the associated metrics and dimensions you need to examine. If you haven’t refreshed your KPIs in the last 6 months or if your business hasn’t created KPIs yet, follow [these instructions](/help/implement/review/define-kpis.md).

## 2. Make sure that your KPI metrics and variables still function well

Remember, code updates over time can have unintended ramifications. You want to make sure that all the metrics and dimensions associated with your [top 5 KPIs](/help/implement/review/define-kpis.md) still function properly. Ideally, this is done right after a website release; if you haven’t done it in the last few months, do it *now*. To do this:

* Create dashboards to see hourly trended views of these critical metrics and variables (or set up [intelligent alerts](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) for each metric). Then monitor them for a day or two to ensure you’re getting the data you expect, and the data is correct. Look for inflection points. Be prepared to remediate any critical issues immediately. If you find any discrepancies, look in your data layer, tag manager rules, and processing rules to find out why.
* Re-run the [Analytics Health Dashboard](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) to monitor broad trends of your KPI metrics and variables.

*For more details about how to make sure that your metrics and variables are functioning properly, [read these tips](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) from Adobe Analytics Champion Sarah Owen.*

## 3. Thoroughly examine the data from the updated section of your site

Ensure that the most recent site release did not adversely impact the data collection for that section of the site: review all the code and variables that correspond to that section to ensure that the new tracking is working as designed.

## 4. Update your documentation

If you have added or changed any metrics or variables recently, you need to update your Business Requirement Document (BRD) and Solution Design Reference (SDR). 

If you don’t have documentation of your implementation, export a list of variables and create your BRD or SDR using [this template](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 5. Immediately address any gaps your find in your data quality

Assess the situation and make a plan to remediate the data. Then make the needed changes, update your documentation, and inform your stakeholders about the changes you made.

*Watch this 2-minute video from Adobe Analytics Champion Sarah Owen about natural times when you can fit reviews of your implementation into your busy schedule:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
