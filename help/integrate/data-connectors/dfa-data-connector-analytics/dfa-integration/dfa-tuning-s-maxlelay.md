---
description: Achieving a successful DFA implementation involves optimizing s.maxDelay for your particular site.
keywords: DFA
seo-description: Achieving a successful DFA implementation involves optimizing s.maxDelay for your particular site.
seo-title: Tuning s.maxDelay
solution: Analytics
title: Tuning s.maxDelay
topic: Data connectors
uuid: 7640af26-6ac6-427e-9cfc-932c86ccf5ab
index: y
internal: n
snippet: y
---

# Tuning s.maxDelay{#tuning-s-maxdelay}

Achieving a successful DFA implementation involves optimizing s.maxDelay for your particular site.

In general, the decision to raise or lower *`s.maxDelay`* involves a tradeoff between obtaining more DFA visitor data and endangering collecting Adobe visitor data. Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. Decreasing s.maxDelay ensures the collection of Adobe visitor data, but could lose DFA visitor data.

*`s.maxDelay`* encapsulates more than just the time in network communication to contact DFA; it also represents browser delays to fire and evaluate the JavaScript from which these communications are based. This is because the Integrate module begins the *`s.maxDelay`* timer after it has inserted the HTML element in to the DOM which pulls the data from the DFA Floodlight server. The amount of time it takes for the browser to actually initiate the HTTP request based on this new HTML element varies based upon other images or JavaScript files that are loading simultaneously, speed of the visitors computer, and specific browser implementations. Furthermore, when the JSON data is retrieved from the DFA Floodlight server, the JavaScript must be evaluated by the browser. This again is controlled completely by the browser and can be delayed if there are large amounts of JavaScript code running simultaneously or many asynchronous JavaScript requests.

With this in mind, *`s.maxDelay`* needs to be set dependent up on the complexity of the landing page plus the amount of network delay with DFA. On some sites, one possible way to decrease complexity is to fire the Adobe collection code early in page loading, so that there is less going on in the browser at the time the Floodlight server is being requested.

The Timeout variable is absolutely required when tuning *`s.maxDelay`*, because it is incremented every time the s.maxDelay timeout is reached. When deciding whether to increase or decrease *`s.maxDelay`* we recommend following this process:

1. Collect several days of data with *`s.maxDelay`* set to a particular value. 
1. Run a [!DNL Daily Unique Visitors Report] for the time range. 
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. Remember that a timeout is only collected once per visitor.

Now having the figures in hand, compute

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Note that the Timeout Percentage is actually considering all visitors to the site. Some of those visitors would not have been tied to DFA at all, and so the timeout is misleading. To improve this computation, another analysis could consider only unique visitors to pages with the `clickThroughParam` set (for example, `?CID=1`). This will show more accuracy.

If the Timeout Percentage is very low, consider decreasing *`s.maxDelay`*. If it is very high, increase *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

Timeouts are expected to decrease when you move to version 2.0 of the integration, because of the eliminations of 302 redirects. Initial findings with beta clients have shown consistent reduction in timeouts, and thus more DFA data being collected 
