---
description: Learn about typical use cases for cohort tables in Analysis Workspace, including app engagement, subscription analysis, campaign stickiness, and product launches.
keywords: Analysis Workspace
title: Cohort Analysis Use Cases
feature: Visualizations
role: User, Admin
exl-id: fc7e7bad-ab57-4bb8-a448-60b9397ef5af
TQID: https://experienceleague.adobe.com/w6aNkoW0CrJNaBLn7XdI84npSxu-5jDJDGmrao4w-GU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: e9cb007b-c8b7-4975-bc81-11a788c535fa
    internal-label: Cohort Analysis
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
    internal-label: Customer engagement
  - id: c13ff12d-60f1-49cd-833a-d43359628223
    internal-label: Mobile messaging
---
# Cohort analysis use cases

This article discusses several typical use cases for which cohort tables are helpful to provide useful insights to take next actions. 

## App engagement

Suppose that you want to analyze how users who install your app engage with the app over time. Do users install the app and never use the app afterwards? Or do they use the app for a while, then stop using the app? Or do the users remain engaged over time?

You can create a six-month cohort analysis. Visitors do not count as *`engaged`* in subsequent months, unless these users have a session or at least launch the app. [!UICONTROL Cohort Analysis] would then show you patterns in usage where *`App Install`* always occurs on Month 0. You might notice that usage dips in month 2, regardless of when users installed the app. This analysis allows you to send an email or a push message to all users during the second month after they install the app to remind them to use the app.

+++ Example cohort table visualization

![App engagement use case](assets/app-engagement.png)

+++

## Subscription

You work at Adobe.com and offer a free Creative Cloud subscription. The goal is for users to upgrade from the free version to the 30-day trial version or, ultimately, the paid version.

Use [!UICONTROL Cohort Analysis] to understand, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. Then 12-15% upgrade in the second month of use. After that, upgrading significantly drops off: 4-5% in month three, 3-4% in month four, and 1-2% in month five.

Recognizing that you do not want to lose potential customers in month three, you set up an email campaign designed to go out in the middle of month three to a sample of users. In that campaign, you offer a $50 coupon to users who have not yet upgraded.

Check back with your cohort analysis a few months later. For cohorts formed after the launch of the campaign, conversion to paid Creative Cloud subscriptions in month three has risen from 4-5% to 13-14%. The conversion results in hundreds of thousands of dollars per cohort, for every monthly cohort that hits month three from that point forward.

+++ Example cohort table visualization

![Subscription use case](assets/subscription-use-case.png)

+++

## Complex cohort segments

You do analysis for a major hotel chain that targets multiple customer groups for promotions and track the customer groups against performance. To identify the best groups of user cohorts to target, you want to create very specific cohort groups. Use the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] tables to define just the right cohort groupings with multiple metrics and segments. This analysis helps you to identify customer groups that underperform so you can target them with promotions and deals to increase bookings.

+++ Example cohort table visualization

![Complex cohort segments use case](assets/complex-cohort-segments.png)

+++

## App version adoption

You are the analyst for a large insurance company that drives customer engagement through the use of its mobile app. As new features are added to the app, customers should upgrade to the latest app version. You can analyze and compare app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. Additionally, you can track retention and churn to see if specific app versions are driving customers away from using the app over time. Through mobile messaging efforts, you can re-engage with these users so the users upgrade to the latest version to take advantage of the latest features.

+++ Example cohort table visualization

![App versus adoption use case](assets/app-versus-adoption.png)

+++

## Campaign stickiness

You are the analyst of a multinational media company that uses targeted campaigns to drive users to their various platforms to drive engagement. Ad spend per platform is based off customer engagement and retention. Successful campaigns are critical to the success of the business. You use the new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. You can then identify which aspects make a campaign successful and apply that knowledge to other campaigns to increase engagement across various platforms.

+++ Example cohort table visualization

![Campaign stickiness use case](assets/campaign-stickiness.png)

+++

## Product launch

You are the analyst for a large apparel retailer that has many specific customer segments that drive large portions of revenue for their business. Each segment has specific products designed and created with the segment in mind. With each product launch, you want to know how the new product has boosted sales to various cohorts over time. Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], you are able to analyze a given customer segment's pre-launch and post-launch behavior and revenue. Using this information, you can identify which products are driving new revenue and which are not gaining traction with customers.

+++ Example cohort table visualization

![Product launch use case](assets/product-launch.png)

+++

## Individual stickiness - most loyal users

You are the analyst of a major airline that derives the majority of their success and revenue from repeat and loyal customers. In many cases, loyal travelers comprise the majority of the revenue and retaining those customers is critical to the long-term success. Identifying the most loyal and consistent customers can often be difficult. However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], you are able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. You are then able to target these travelers with rewards and perks for their loyalty. Additionally, by switching the cohort type from retention to churn, you are also able to identify which customers were not repeat purchasers month-over-month. Then you can target those segments with promotions to re-engage with these customers so these customers remain loyal in the future.

+++ Example cohort table visualizations

![Individual stickiness use case - retention](assets/individual-stickiness-1.png)

![Individual stickiness use case - churn](assets/individual-stickiness-2.png)

+++
