---
description: Learn about how time-parting dimensions take the timestamp of collected events and breaks down these events into more meaningful dimensions, such as Hour of Day or Day of Week.
title: Time-Parting Dimensions
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
TQID: https://experienceleague.adobe.com/bQVBmv3KhaDZtmUXSOY3UsustpCZKAwJ8rH9Qv49Rfw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Time-parting dimensions

Time parting takes the timestamp of collected hits and breaks it into more meaningful dimensions, such as **Hour of Day** or **Day of Week**.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Time-parting dimensions](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/time-parting-dimensions-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


Time-parting dimensions are based on the time zone of the report suite or virtual report suite. These dimensions are available in Analysis Workspace and can help to answer the following questions:

* Across a large date range, what is the most popular time of day for visitors to access my site or app? 
* Are there days of the week, or hours of the day, on which conversion is higher on my site or app? 
* How do my weekend sales compare to my weekday sales? 
* Does a certain marketing campaign generate higher conversions in the morning, or in the afternoon?

>[!NOTE]
>
>Time-parting dimensions are only available in Analysis Workspace. To use time-parting dimensions in other Analytics solutions, you can implement the [getTimeParting plug-in](/help/implement/vars/plugins/gettimeparting.md).

Time-parting dimensions in Analysis Workspace include: 

| Dimension | Example Values |
| --- | --- |
| Hour of Day | 0-23 |
| AM/PM | AM, PM |
| Day of Week | Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday |
| Weekend/Weekday | Weekend, Weekday |
| Day of Month | 1-31 |
| Month of Year | January-December |
| Day of Year | 1-366 |
| Quarter of Year | Q1, Q2, Q3, Q4 |
