---
description: null
seo-description: null
seo-title: Fallout overview
title: Fallout overview
uuid: a184933d-93c1-42c1-b9c0-6931b478ff94
index: y
internal: n
snippet: y
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

## Segmentation as a foundation for flow and fallout {#section_654F37A398C24DDDB1552A543EE29AA9}

Segments applied to Workspace panels work slightly differently than segments applied to fallout and flow reports in Reports & Analytics or Ad Hoc Analysis. Most of the time, they provide exactly the same results. The main difference is that Reports & Analytics and Ad Hoc Analysis apply the segment at each step of the sequence. This can result in slightly different outcomes.

Let's take an example of fallout with two steps:

![](assets/fallout_segments1.png)

If you then apply a segment at the Workspace panel level, the segment combines with the fallout like this:

![](assets/fallout_segments2.png)

By contrast, when Reports & Analytics and Ad Hoc Analysis calculate the segment, the segment is combined this way:

![](assets/fallout_segments3.png)

Reports & Analytics and Ad Hoc Analysis combine the segment with each step. When the containers are at the same level as the fallout (e.g. visit or visitor level) this will result in matching the number of visits or visitors.

However, if the segment applied to the panel is smaller than the level of the fallout (e.g. hit level), then the segment will show different results because of how it is combined by the report. To reiterate, under most circumstances the numbers in Analysis Workspace match those in Reports & Analytics and Ad Hoc Analysis. They will **not** match only if all of the cases below are true:

* The segment isn’t at the same level as the fallout. 
* The segment has a variable where the visitor/visit can have multiple values during a visit/visitor.

In the rare case where you need to have Analysis Workspace match the Reports & Analytics way of applying segments to fallout/flow, simply drop the segment into each fallout step in Workspace and it will result in the same numbers. 
