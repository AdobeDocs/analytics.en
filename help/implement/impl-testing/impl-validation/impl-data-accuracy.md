---
description: Data accuracy validation is a process of comparing report data with known and verifiable data points.
keywords: Analytics Implementation
seo-description: Data accuracy validation is a process of comparing report data with known and verifiable data points.
seo-title: Data accuracy validation
solution: Analytics
title: Data accuracy validation
topic: Developer and implementation
uuid: 267f6c61-705a-41cf-9e09-4e2ce2331f32
index: y
internal: n
snippet: y
---

# Data accuracy validation

Data accuracy validation is a process of comparing report data with known and verifiable data points.

The validation process should be completed by Adobe personnel, preferably by the Adobe Consultant (the person most familiar with the technical implementation details).

The preferred data points for this validation, in order of preference, are listed as follows:

* (Econversion sites) Comparison of econversion orders for a single day. 
* Comparison of known success events, especially logged data where IP address and other browser information generally stored in web server logs can be compared to the data collected. 
* Comparison of page views.

>[!NOTE]
>
>Default pages, such as [!DNL index.html], often receive automated or monitoring traffic. These pages represent a greater difference to browser-based data collection than other visited pages.

All three types of validation require a debug log or data feed for the time period in question. This is generally one day or less.

It is expected that orders or success events can be measured to within 2-3% of actual values (sometimes reaching higher accuracy levels) using standard JavaScript-based implementations. This assumes an SSL page, since SSL pages are cached much less frequently, and by definition they should not be cached. An implementation with fully server-side image requests on an SSL page should come within about 0-1% of actual values. Non-secure pages may experience higher differences, but still within 5% of actual values.

When comparing page views for a single time period, it is expected that the page views can be accounted for within 5% of actual values, not including monitoring (such as Keynote or WhatsUpGold) or automated traffic (spiders, bots, and scripts).

Data accuracy comparisons need to take into account the following items:

* QA or other types of internal testing that may be filtered by IP addresses or VISTA rules. 
* Smart tags that only generate tags for certain types of orders or traffic. 
* Queries for comparison must take into account what is being measured by the website (not including returns, orders placed by customer service personnel, or other special conditions). 
* Ensure that the time zone differences between the query and the report suite match. 
* Custom Keynote or similar traffic (Keynote Transaction, etc.) that measure the ordering process and may be reflected in tags, but removed from ordering systems. 
* Account for the client's de-duping processes. 
* Reloads of the order page (Orders are de-duplicated based on *`purchaseID`*).

