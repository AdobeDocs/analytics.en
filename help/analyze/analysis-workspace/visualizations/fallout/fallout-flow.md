---
description: Use the fallout visualization in a Workspace project.
title: Fallout overview
uuid: 2d98899e-e401-4d7a-8af0-de0002f84178
feature: Visualizations
role: Business Practitioner, Administrator
exl-id: 85d0c88e-d159-4870-aaf6-51899d87ff77
---
# Fallout overview

Fallout visualizations provide more options to build your fallout reports. Fallout reports show where visitors left (fell out) and continued through (fell through) a predefined sequence of pages.

Fallout visualizations let you

* Perform side-by-side comparisons of two different segments in the same report.
* Drag, drop, and rearrange funnel steps (touchpoints) 
* Mix and match values from different dimensions and metrics 
* Create a multi-dimensional fallout report 
* Identify where customers go immediately after falling out

Fallout displays conversion and fallout rates between each step or touchpoint in a sequence.

For example, you can track a visitor's fallout points during a purchase process. Just select a beginning touchpoint and a conclusion touchpoint, and add intermediate touchpoints to create a website navigation path. But you can also do multi-dimensional fallouts.

A fallout visualization is useful for analyzing:

* Conversion rates through specific processes on your site (such as a purchase or registration process).
* General, wider-scope traffic flows: Of the people who saw the home page, this flow shows how many went on to perform a search, and then how many of them eventually went on to look at a specific item.
* Correlations between events on your site. Correlations show what percentage of people who looked at your privacy policy went on to purchase a product.

[Fallout Visualization video tutorial](https://experienceleague.adobe.com/docs/ analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html) (4:15)

## Segmentation as a foundation for flow and fallout {#section_654F37A398C24DDDB1552A543EE29AA9}

Segments applied to Workspace panels work slightly differently than segments applied to fallout and flow reports in Reports & Analytics. Most of the time, they provide exactly the same results. The main difference is that Reports & Analytics applies the segment at each step of the sequence. This can result in slightly different outcomes.

Let's take an example of fallout with two steps:

![](assets/fallout_segments1.png)

If you then apply a segment at the Workspace panel level, the segment combines with the fallout like this:

![](assets/fallout_seg.png)

By contrast, when Reports & Analytics calculates the segment, the segment is combined this way:

![](assets/fallout_segments3.png)

Reports & Analytics combines the segment with each step. When the containers are at the same level as the fallout (e.g. visit or visitor level) this will result in matching the number of visits or visitors.

However, if the segment applied to the panel is smaller than the level of the fallout (e.g. hit level), then the segment will show different results because of how it is combined by the report. To reiterate, under most circumstances the numbers in Analysis Workspace match those in Reports & Analytics. They will **not** match only if all of the cases below are true:

* The segment isn't at the same level as the fallout.
* The segment has a variable where the visitor/visit can have multiple values during a visit/visitor.

In the rare case where you need to have Analysis Workspace match the Reports & Analytics way of applying segments to fallout/flow, simply drop the segment into each fallout step in Workspace and it will result in the same numbers.
