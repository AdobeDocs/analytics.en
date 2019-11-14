---
description: If you want to track additional information, but don't have enough variables to do so, you now have access to additional eVars and success events 
keywords: Analytics Implementation;evars;events;evars number;how many evars;how many events
solution: Analytics
title: Additional eVars and events
topic: Developer and implementation
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
---

# Additional eVars and events

If you want to track additional information, but don't have enough variables to do so, you now have access to additional eVars and success events:

> [!NOTE] JavaScript H-Code does not support these additional eVars and events.

## Entitlements to Custom Dimensions and Events {#section_869EC3D8A5614036A9C586F2B74FA7DC}

|  Adobe Analytics Product  |  |  |  |
|---|---|---|---|
|  Adobe Analytics - Foundation  | 75 props  | 200 eVars  | 1000 Events  |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html)  | 75 props  | 200 eVars  | 1000 Events  |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html)  | 75 props  | 200 eVars  | 1000 Events  |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html)  | 75 props  | 250 eVars  | 1000 Events  |

## Populating Variables and Events {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Variables can be populated in the data collection library if you are using these versions of [!DNL AppMeasurement]:

    * AppMeasurement for JavaScript version 1.4+ 
    * AppMeasurement for Flash version 3.9+ 
    * AppMeasurement for Java version 1.2.8+ 
    * AppMeasurement for Silverlight/.NET version 1.4.2+ 
    * AppMeasurement for PHP version 1.2.2+

* If you are on an earlier version of code, or on JavaScript H.&#42;, you can populate context data and use processing rules to populate variables.
* All versions of data collection code can populate events 101-1000.
* Processing rules can be used to populate eVars 76-250 based on context data or other variables.

## Frequently Asked Questions {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **Will all Adobe Analytics interfaces have immediate access to these new variables?** These interfaces will have immediate access: [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], [!UICONTROL Ad Hoc Analysis], APIs, and [!UICONTROL Data Workbench].

* **Will these additional eVars and events automatically show up in my data feeds?** Data feeds will have access to the new variables and events once enabled. New eVar columns will not appear until you choose to include them. However, new events will appear in the event_list column as soon as they're enabled, and the events lookup table contains the event names for those event IDs. Do not enable new events unless you are ready to consume them in Data Feeds.

* **How do I request new data feed columns?** To request new columns, refer to [Configuring Data Feeds](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html).

* **What if I am an Analytics Ultimate customer who wants to go back to Analytics Prime and I currently have more than 200 eVars enabled?** Adobe will not disable any of your existing eVars, but you will not be able to enable more. If you disable eVars, you cannot turn them back on until you are below the Analytics Prime limit of 200 enabled eVars.

