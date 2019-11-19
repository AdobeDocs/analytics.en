---
description: Adobe Analytics offers various Time Spent metrics and dimensions. Find out what they are and how they are calculated.
solution: Analytics
title: Time Spent
topic: Metrics
---

# Time spent 

Various 'time spent' metrics and dimensions are offered across Adobe Analytics products.

## 'Time spent' metrics

|Metric|Definition|Available in|
|---|---|---|
|Total seconds spent|Represents the total amount of time visitors interact with a specific dimension item. Includes the instance of a value & persistence across all subsequent hits. In the case of props, time spent is counted across subsequent link events as well.|Analysis Workspace, Reports & Analytics, Report Builder (called ‘total time spent’), Data Warehouse|
|Time spent per visit (Seconds)|*Total seconds spent / (visit-bounces)*<br>Represents the average amount of time visitors interact with a specific dimension item during each visit.|Analysis Workspace, Reports & Analytics|
|Time spent per visitor (Seconds)|*Total seconds spent / unique visitor*<br>Represents the average amount of time visitors interact with a specific dimension item across the visitor’s lifetime (length of their cookie).|Analysis Workspace, Reports & Analytics|
|Average time spent on site (Seconds)|Represents the total amount of time visitors interact with a specific dimension item, per sequence with a dimension item. It is not just limited to “site” averages as the name suggests. See the "How Time Spent is Calculated" section for more information on sequences.<br>**Note**: This metric very likely differs from 'Time Spent per Visit' at a dimension item level due to the differences in the denominator in the calculation.|Analysis Workspace, Reports & Analytics (shown in minutes), Report Builder (shown in minutes)|
|Average time spent on page|Deprecated metric.<br> Instead, we recommend that you use ‘Average time spent on site’ if average time for a dimension item is needed.|Report Builder (when a dimension is in the request)|
|Total session length, a.k.a. Previous session length|Mobile App SDK only. <br>Determined the next time the app is launched, for the previous session. Calculated in seconds, this metric does not count when the app is in the background, only when in use. This is a session-level metric.<br>Example: We install app ABC and launch and use it for 2 minutes and then close the app. No data is sent about this session time. The next time we launch the app, Previous Session Length will be sent with a value of 120.|Analysis Workspace, Reports & Analytics, Report Builder, Mobile Services UI |
|Average session length (mobile)|*Total Session Length / (Launches – First Launches)*<br>Mobile App SDK only. This is a session-level metric.|Report Builder, Mobile Services UI|

## 'Time spent' dimensions

|Dimension|Definition|Available in|
|---|---|---|
|Time spent per visit - granular|The total time spent during the visit truncated to the nearest second, and applied to every hit that was part of the visit. This is a visit-level dimension.|Analysis Workspace|
|Time spent per visit - bucketed|The granular dimension bucketed into 9 different ranges. This is a visit-level dimension. Ranges include:<ul><li>Less than 1 minute</li><li>1-5 minutes</li><li>5-10 minutes</li><li>10-30 minutes</li><li>30-60 minutes</li><li>1-2 hours</li><li>2-5 hours</li><li>5-10 hours</li><li>10-15 hours</li></ul>**Note**: There cannot be buckets higher than this, because a visit expires after 12 hours of activity.|Analysis Workspace, Reports & Analytics, Report Builder|
|Time spent on page - granular|The total time spent on each hit, truncated to the nearest second. This is a hit-level dimension and includes both page views and link events. Despite its name, it is not limited to the “page” dimension.|Analysis Workspace|
|Time spent on page - bucketed|The granular dimension bucketed into 10 different ranges; however, the bucketed dimension only counts page views (and excludes link events). This is a hit-level dimension. Ranges include:<ul><li>less than 15 seconds</li><li>15 to 29 seconds</li><li>30 to 59 seconds</li><li>1 to 3 minutes</li><li>3 to 5 minutes</li><li>5 to 10 minutes</li><li>10 to 15 minutes</li><li>15 to 20 minutes</li><li>20 to 30 minutes</li><li>more than 30 minutes</li></ul>|Analysis Workspace, Reports & Analytics|

## How 'Time Spent' is calculated

Adobe Analytics uses explicit values (including link events and video views) to calculate Time Spent.

>[!NOTE]
>
>Without link events like Video Views or Exit Links, time spent on the last hit of a visit cannot be known. For similar reasons, 'bounce visits' (i.e. visits with a single hit) also does not have a 'time spent' associated with it.

The **numerator** in all time spent calculations is total seconds spent.

The **denominator** is not available as a separate metric in Analytics. For hit-level 'time spent' metrics, the denominator is sequences. A sequence is a consecutive set of hits where a given variable contains the same value (whether by being set, spread forward, or persisted). 'Spread forward' refers to the persistence of props between page views (i.e. across subsequent link events), for the purposes of calculating time spent.

* For example, in the case of 'Page Name' or other dimensions at the hit level, the denominator is essentially 'Instances' or 'Page Views', but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence). 

* Bounce and exit hits are also removed from the denominator because 'time spent' cannot be known.

## FAQs

**Q1: Can all time spent metrics be applied to any dimension?**
A: The 'time spent' metrics that can be applied to any dimension are:

* Total seconds spent

* Time spent per visit (Seconds)

* Time spent per visitor (Seconds)

* Average time spent on site (Seconds)

**Q2: Which time spent dimension is best used in breakdowns with other dimensions?**
A: The “Time Spent on Page – granular” dimension is a hit-level dimension. Breaking this down by another dimension will tell you the seconds that a hit lasted where the breakdown dimension was also present. 
In the example below, the search term “classifieds” is associated with hit times of 54 seconds, 59 seconds, etc, perhaps indicating visitors are spending time reading content returned for that term.

![](assets/time-spent1.png)
 
**Q3: What metric is appropriate against the dimension of “Time Spent on Page – granular”?**
A: Any metric. The dimension will show the time spent on the exact hit where the event occurred. Higher time spent means a visitor stayed longer on a page (hit) where the event occurred.

![](assets/time-spent2.png)

**Q4: How does Average Time Spent on Site differ from Time Spent per Visit?**
A: The difference is the denominator in the metric:

* Average time spent on site uses the sequences that include a dimension item.

* Time spent per visit uses the visit count

As a result, these metrics may yield similar results at a visit level, but will be different at a hit level.

