---
title: Schedule a traffic spike
description: Partner with Adobe to make sure high-traffic events don't experience latency.
feature: Traffic Management
exl-id: a6bbd975-6d31-40f5-8f80-491ec3a5c5f5
---
# Schedule a traffic spike

Adobe attempts to partner with clients to ensure that a high-traffic event is successful. Scheduling traffic spikes is the starting point in that partnering process. The Schedule Spike section lets you alert Adobe of temporary traffic spikes so that appropriate resources can be allocated to handle them. You can estimate past server calls to get a better idea of the size of traffic spike you need to schedule.

Advanced server-side data balancing with several dedicated personnel are used to make sure that all customers have the most up-to-date reports possible. As your organization notifies Adobe of spikes in traffic, Adobe can make sure that the sudden increase in traffic is a positive experience. Failure to notify Adobe of increases in traffic can increase latency during critical reporting periods.

{{$include /help/_includes/traffic-lead-time.md}}

## Schedule a traffic spike

To schedule a traffic spike: 

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Report suites]**.
1. Select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Traffic Management]** > **[!UICONTROL Schedule Spike]**.
1. (Optional) You can estimate past server calls to get a better idea of how the size of traffic spike you need to schedule.

   For example, You can get last year's daily server call average during a specific time frame, plus an expected increase in server call volume for this year. You can then schedule a traffic spike based on this multiplication factor.

   1. In the **[!UICONTROL Past Server Calls]** area, select a start and end date for the selected report suites.

      The amount for [!UICONTROL **Peak Day**], [!UICONTROL **Peak Day Server Calls**], and [!UICONTROL **Daily Average of Server Calls**] is generated.

   1. Input a value for the multiplication factor, then select **[!UICONTROL Click to multiply and set]**.

      The value for each of the columns is multiplied for each report suite.
1. In the [!UICONTROL **Set Spike Parameters**] area, in the **[!UICONTROL Spike Start Date]** field, specify the date when you expect the traffic spike to start.
1. In the **[!UICONTROL Spike End Date]** field, specify the date when you expect the traffic spike to end.
1. In the **[!UICONTROL Peak Day Server Calls]** field, specify the total expected peak page views per day during the traffic spike period.
1. In the **[!UICONTROL Peak Hour Server Calls]** field, specify the total expected peak page views per hour during the traffic spike period.
1. Select **[!UICONTROL Submit]**.

   Make sure to specify the total expected page views, not just the additional page views.

   >[!NOTE]
   >
   >To schedule a traffic spike, include a phone number in your user contact information so that Adobe can contact you with questions, if needed.

## Why it is important to always schedule traffic spikes

When customers notify Adobe of traffic spikes for each report suite, Adobe does everything possible to ensure that it has a minimal impact on reporting.

* Organizations that have scheduled traffic spikes receive priority if data starts going latent. The importance of this concept is especially critical during the holiday season, as many organizations schedule traffic spikes.
* If Adobe notices that you significantly overestimated/underestimated expected traffic compared to previous years, they can contact you to ensure accuracy.
* It is important to schedule a traffic spike every year, even if your organization receives the same spike each year. Many organizations release new apps, combine report suites, and migrate/retire report suites throughout the year. Adobe has no way of knowing for certain which report suites receive extra traffic unless your organization schedules a traffic spike each time. While Adobe uses historical data to get an estimate, it is important that any extra resources are placed on the right report suite.

## Actions your organization can take

Adobe wants to make sure that your experience with up-to-date reporting is consistent. To do this task most effectively, Adobe highly recommends the following:

* Schedule lead time for all traffic spikes. **It is especially important that any traffic spikes anticipated in the months of November-December are scheduled by September 15**. If you miss the deadline, schedule your spike as soon as possible. Less lead time is better than none, and Adobe works with the current resources to best accommodate your report suites.
* If Adobe contacts you regarding a scheduled traffic spike, be sure to communicate if real-time reporting or full processing reporting is more important. Some organizations rely on Real-Time reporting more than others. Understanding which type of reporting you use can help Adobe prioritize accordingly.
* Communicating with your Account Manager the most important reports and when you pull them can help them advocate for you.
