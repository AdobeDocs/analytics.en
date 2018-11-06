---
description: Shows the most common links people are clicking on that lead to places outside your site. These links typically point to partner or affiliate sites. However, they can be any location where you have implemented an external link. You can use this report to view the most popular affiliate links, or to assist in validating the number of referrals that your partners' state you provide.
seo-description: Shows the most common links people are clicking on that lead to places outside your site. These links typically point to partner or affiliate sites. However, they can be any location where you have implemented an external link. You can use this report to view the most popular affiliate links, or to assist in validating the number of referrals that your partners' state you provide.
seo-title: Exit Links
solution: Analytics
title: Exit Links
topic: Reports
uuid: e1452f04-389d-4aa3-8763-732880284302
index: y
internal: n
snippet: y
---

# Exit Links

Shows the most common links people are clicking on that lead to places outside your site. These links typically point to partner or affiliate sites. However, they can be any location where you have implemented an external link. You can use this report to view the most popular affiliate links, or to assist in validating the number of referrals that your partners' state you provide.

There are several requirements that must be met in order for this page to populate correctly:

* If using manual custom link tracking, an *`s.tl()`* request must be fired with the middle parameter set to *e*. 

* If using automatic custom link tracking, all requirements must be met: 
*

    * [s.trackExternalLinks](http://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_trackexlinks) must be set to *true*. 
    
    * The link the user clicked on must not match any values within the [s.linkInternalFilters](http://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) variable. 
    * If [s.linkInternalFilters](http://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) is implemented, the external link must match at least one of the values set in this variable.

* If any of the above requirements are not met, the hit will not populate this report.

* 
* As with all custom link tracking hits, the [s.pageName](http://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) variable is stripped from the image request to prevent page-view inflation. 
* You can view this report in trended and ranked formats. 
* This report can use a search filter to locate specific line items. 
* You can create [correlations](correlation.md#concept_B33A589E121D4E9BB51DAA8A2C324758) with any other traffic variable via Admin Tools. 
* [Instances](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) are the only metrics available by default within this report, counting the number of times the exit link fired. 
* Daily, weekly, monthly and quarterly visitors can be enabled for this report. However, only an Adobe representative can enable these, at an additional cost. Enabling unique visitors for any custom link tracking variables greatly increases latency for the report suite.

