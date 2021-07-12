---
description: Use case examples for cohort analysis.
keywords: Analysis Workspace
title: Cohort analysis use cases
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
feature: Visualizations
role: User, Admin
exl-id: fc7e7bad-ab57-4bb8-a448-60b9397ef5af
---
# [!UICONTROL Cohort Analysis] use cases

Use case examples for [!UICONTROL Cohort Analysis].

## App engagement use case {#section_ADEC6EE79F1846319B2E0D9544CC5E40}

Suppose that you want to analyze how users who install your app engage with it over time. Do they install it and never use it? Do they use it for a while, then fall away? Or do they remain engaged over time?

You can create a six-month [!UICONTROL Cohort Analysis]:

**Granularity**: Monthly, from January 2015 through June 2015.

**Inclusion metric**: App Installs.

**Return metric**: Sessions or Launches

Visitors do not count as *`engaged`* in subsequent months unless they are having a session or at least launching the app. [!UICONTROL Cohort Analysis] would then show you patterns in usage where *`App Install`* always occurs on Month 0. You might notice that usage dips in Month 2, regardless of when users installed the app. (For those who installed the app in January 2015, Month 2 is March 2015. For those who installed the app in February 2015, Month 2 is April 2015, and so on.) This analysis allows you send an email or a push message to all users during the second month after they install the app to remind them to use the app.

## Subscription use case {#section_FDECB16766CF415BB84AE46BA491FB5F}

You work at Adobe.com and offer a free Creative Cloud subscription. The goal is for users to upgrade from the free version to the 30-day trial version or, ultimately, the paid version.

**Granularity**: Monthly

**Inclusion metric**: Download Link

**Return metric**: Purchase Paid Creative Cloud

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. 12-15% upgrade in the second month of use. After that, upgrading significantly drops off: 4-5% in month three, 3-4% in month four, and 1-2% in month five.

Recognizing that you need to not lose potential customers in month three, you set up an email campaign designed to go out in the middle of month three to a sample of users, offering a $50 coupon to users who have not yet upgraded.

Check back with your cohort analysis report a few months later. For cohorts formed after the launch of the campaign, conversion to paid Creative Cloud subscriptions in month three has risen from 4-5% to 13-14%, resulting in hundreds of thousands of dollars per cohort, for every monthly cohort that hits month three from that point forward.

## Complex Cohort Segments use case

A major hotel chain targets multiple customer groups for promotions and tracks against performance. In order to identify the best groups of user cohorts to target, they want to create very specific cohort groups. Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## App Version Adoption use case

A large insurance company drives a lot of customer engagement through the use of its mobile app. However, as new features are added to their app, it is critical that their customers upgrade to the latest app version. They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. Additionally, they can track both retention and churn to see if specific app versions are driving customers away from using the app over time. Through mobile messaging efforts, they can re-engage with these users to get them to upgrade to the latest version to take advantage of their latest features.

## Campaign Stickiness use case

A multinational media company uses targeted campaigns to drive users to their various platforms to drive engagement. Ad spend per platform is based off customer engagement and retention; therefore, successful campaigns are critical to the success of their business. They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. They can then identify which aspects make a campaign successful and apply it to other campaigns to increase engagement across their various platform.

## Product Launch use case

A large apparel retailer has many specific customer segments that drive large portions of revenue for their business. Each segment has specific products designed and created with the segment in mind. With each product launch, they want to know how the new product has boosted sales to various cohorts over time. Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], they are able to analyze a given customer segment's pre-launch and post-launch behavior and revenue. Using this information, they can identify which products are driving new revenue and which are not gaining traction with customers.

## Individual Stickiness - Most Loyal Users use case

A major airline derives the majority of their success and revenue from repeat and loyal customers. In many cases, their loyal travelers comprise the majority of their revenue and retaining those customers is critical to their long-term success. Identifying their most loyal and consistent customers can often be difficult. However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. They were then able to target these travelers with rewards and perks for their loyalty. Additionally, by switching the Cohort type from retention to churn, they were also able to identify which customers were not repeat purchasers month-over-month and target those segments with promotions in order to re-engage with them and ensure they remain loyal customers in the future.
