---
description: Learn about data anomaly detection in Analysis Workspace.
title: Anomaly Detection Overview
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
---
# Anomaly detection overview

You can view and analyze data anomalies contextually within Analysis Workspace. Contribution Analysis works with Anomaly Detection to help identify what contributed to the anomaly. 


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Anomaly detection](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Adobe Analytics Select and Adobe Analytics Foundation customers have access only to *daily granularity* Anomaly Detection in Workspace. For more information, see [Anomaly Detection and Contribution Analysis Entitlements](#anomaly-detection-and-contribution-analysis-entitlements).

## Anomaly detection

Anomaly Detection provides a statistical method to determine how a given metric has changed in relation to previous data.

Anomaly Detection allows you to separate "true signals" from "noise" and then identify potential factors that contributed to those signals or anomalies. In other words, it lets you identify which statistical fluctuations matter and which don't. You can then identify the root cause of a true anomaly. Furthermore, you can get reliable metric (KPI) forecasts.

Examples of anomalies you might investigate include:

* Drastic drops in average order value
* Spikes in orders with low revenue
* Spikes or drops in trial registrations
* Drops in landing page views
* Spikes in video buffer events
* Spikes in low video bit-rates

Both Anomaly Detection and [Contribution Analysis](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/anomaly-detection/anomaly-detection) are core workflows in Analysis Workspace. You can run Contribution Analysis against any daily anomaly and embed the result in your Analysis Workspace project.

Analysis Workspace's anomaly detection algorithm includes

* Support for hourly, weekly, and monthly granularity, in addition to the existing daily granularity.
* Awareness of seasonality (such as "Black Friday") and holidays.

## Contribution Analysis

Contribution Analysis discovers hidden patterns within your data to explain statistical anomalies and identify correlations behind

* unexpected customer actions, 
* out-of-bound values, and 
* sudden spikes or dips 

for selected metrics across convergent audience segments.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Contribution analysis](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


Something happened. Why? Your Anomaly Detection report shows an unusual spike in orders and you want to know why. What happened out of the ordinary? Who is responding to what campaign or referral? Did something go viral? What are the specific factors that contributed to this anomaly? And perhaps most importantly: How can I capture important information about my customer and repeat this performance? (Or, if a dip in a metric or rise in a negative metric occurred, how can I avoid it in the future?)

Contribution Analysis helps you evaluate your data immediately to answer why an anomaly happened. It breaks down the contributions to an anomaly in seconds in what used to take weeks, providing patterns for audience segments and helping you develop a narrative for customer interactions. You can employ Contribution Analysis strategically to identify and capture meaningful associations. Then use those associations strategically to develop new audience segments, or tactically to identify out-of-bound or fraudulent activity that triggers an alert.

[Anomaly Detection](#anomaly-detection) identifies data spikes and extreme statistical dips based on selected metrics and selected audience segments. Anomaly detection sets a historical norm based on a training period and then plots extreme offsets that correlate to specific events. Anomaly detection can report a precipitous rise in a positive Orders metric or a rise in a negative Bounces metric, or dips in both, capturing statistically relevant data points to be evaluated by Contribution Analysis. Once a statistical anomaly is identified, Contribution Analysis lets you drill down and evaluate relevant marketing and campaign variables across all anomalous data points. It runs advanced algorithms and machine-learning processes to evaluate associations that contributed to a significant spike or dip. These calculations are then displayed in interactive visualizations designed to give you varying perspectives to help answer why something happened, and what to do about it.

Contribution Analysis helps you develop a narrative to describe why an anomaly occurred. And how to respond to anomalies, capturing relevant metrics and identifying hidden points that give you an overall reason for audience interactions and trending customer interests. Sometimes an anomaly is easy to see and correct, such as an errant order for 2,000 kayaks. Sometimes it's complex, like identifying an emerging trend across a time period in a region reacting only to a specific targeted campaign. Piecing together contributing items across metrics for various dimensions and their associations gives you an overall idea of your audience interactions and helps provide context for anomalous data points.

Here are a few use cases:

* Identify re-marketing potential by monitoring changes in product demand.
* Enhance customer experience by reacting to specific audience interests.
* Identify fraudulent orders early as an out-of-bounds report.
* Protect yourself from corporate espionage by identifying high usage and downloads.
* Monitor operations such as reporting missing JavaScript tags.

After a comprehensive analysis of an anomaly, a Contribution Summary is generated for Top Items ordered by total occurrences and the item's percentage of the contributing values. A normalized Contribution Score lets you easily compare, contrast, and associate with other significant dimension items.

## Contribution Analysis tokens

All customers with a Contribution Analysis entitlement can run full Contribution Analysis a limited number of times per month in Analysis Workspace. Contribution Analysis **excludes** point product (SiteCatalyst 15) customers, Analytics Foundation customers, and Analytics Select customers, who are not entitled to Contribution Analysis.

The number of runs per company is limited by monthly tokens that are granted based on the Adobe Analytics product your company purchased. The number of runs per company includes the ability to restrict Contribution Analysis access to avoid token misuse.

## Frequently asked questions

| Question | Answer |
| --- | --- |
| Why did Adobe introduce tokens? | Contribution Analysis has been one of the most resonant capabilities in Adobe Analytics. Giving you a small number of full runs per month (rather than just 3 dimensions for some Analytics products) allows you to see what unlimited full Contribution Analysis can do for you. |
| How do tokens in Contribution Analysis work? Does it cost a token to load a project with an existing Contribution Analysis, or only when running a brand new one? | Each login company (not each user) gets a certain number of tokens per month, which allow you to run "complete" Contribution Analysis in Analysis Workspace.  Each time you generate a new Contribution Analysis, you pay one token. Loading projects with pre-run Contribution Analyses does not cost a token. |
| If my company is out of tokens and wants to run additional Contribution Analyses, what to do? | You can upgrade to another Adobe Analytics product, for example from Standard (2 tokens/month) to Ultimate (20 tokens/month). You cannot buy more tokens. You must upgrade within the existing packaging framework. |
| How do I restrict access to Contribution Analysis? | By default, only admins have access to run Contribution Analyses. However, admins can grant access to other users by creating a permission group in the [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/home). Give permission to use Contribution Analysis only to users who have a legitimate reason to use it and are trusted not to abuse their access. The permission is called [!UICONTROL Contribution Analysis] under [!UICONTROL Report Suite Tools]. [Learn more](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/permissions/report-suite-tools) |
| How do I know how many tokens my company is entitled to per month, and how many tokens my company have used in the current month? | Go to  [!UICONTROL Admin] > [!UICONTROL All admin] >[!UICONTROL Company settings Home] >[!UICONTROL View Feature Access Levels]. Look under<ul><li>Contribution Analysis: Number of Monthly Usage Tokens</li><li>Contribution Analysis: Number of Usage Tokens used this month</li></ul> |

## Anomaly Detection and Contribution Analysis entitlements

Below is a list of the detailed entitlements for Anomaly Detection and Contribution Analysis in Analysis Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics Entitlement </th> 
   <th colname="col2" class="entry"> Anomaly Detection </th> 
   <th colname="col3" class="entry"> Contribution Analysis </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Daily granularity only </p> </td> 
   <td colname="col3" colsep="1"> <p>No tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>Daily granularity only </p> </td> 
   <td colname="col3"> <p>No tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&mv=other"  > Prime </a> </p> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>10 tokens per month </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>20 tokens per month </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Predictive Workbench add-on </p> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>Unlimited tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>2 tokens per month </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Attribution) </p> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>2 tokens per month </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete, <a href="https://business.adobe.com/products/analytics/predictive-analytics.html"  > Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>Unlimited tokens </p> </td> 
  </tr> 
 </tbody> 
</table>
