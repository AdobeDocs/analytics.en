---
title: Attribution best practices
description: What are the best practices around deciding on an attribution model?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
---
# Attribution best practices

Picking the right attribution model for your organization depends on a number of considerations. This article explores a methodology and some general best practices. 

## Step 1: Exploratory Analysis

>[!NOTE]
>This analysis needs to happen before you pick an attribution model.

This phase consists initially of understanding customer behavior and defining conversion metrics. Based on the conversion metrics, tools like [Data Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html) (for raw data) or Analysis Workspace facilitate your understanding of

* How many customers are touching different marketing channels before converting?
* The proportion/distribution of these behaviors. 

For example, if 50% of customers touch 3 channels before converting, is there any interaction among those 3 channels?
You could then do upper- and lower-funnel analysis to expand your understanding. 

### Upper-funnel analysis

Upper-funnel analysis analyses channels used to create brand or product awareness. For example, the goal of most TV ads is brand awareness. You might use the ["Time decay" attribution model](/help/analyze/analysis-workspace/attribution/models.md), since people will forget about your TV ad over time.

### Lower-funnel analysis

In this analysis, the assumption is that people already know about your brand and you want them to convert. Use e-mail or push notifications or Facebook ads.

## Step 2: Rule-base attribution

The purpose of this step is to validate your hypotheses. 

**Example 1**

Let's say your hypothesis is "My First-touch channel has more impact on conversion than my last-touch channel. You would then use the ["Inverse J-shaped" attribution model](/help/analyze/analysis-workspace/attribution/models.md) to test this hypothesis. This model gives 60% of the credit to the first touch point.

**Example 2** 

Your hypothesis might be: "In our industry (such as travel industry), the attribution window is 60 or 90 days, not 30 days, because customers do a lot of research before buying a product. You would then change your [lookback window](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html#lookback-windows) to 90 days. 

## Step 3: Use Algorithmic attribution

Because it is very hard to validate a large number of possible hypotheses and combinations, you can use [algorithmic attribution](/help/analyze/analysis-workspace/attribution/algorithmic.md) to leave this work to built-in algorithms. If you have already found the perfect attribution model that answers all your questions and is a perfect fit, then you obviously don't need to take this step.

## Other considerations

* You might need to use the services of a data scientist instead of relying on Analysis Workspace alone.
* You can rely on raw data, as in Adobe data feeds.
* Consider using [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html), for example, if you want to consider your Impressions data.
