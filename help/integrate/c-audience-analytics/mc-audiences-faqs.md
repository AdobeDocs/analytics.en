---
description: Answers to questions you might have when implementing Audience Analytics.
solution: Experience Cloud
title: Frequently Asked Questions for Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
---
# Frequently Asked Questions

Answers to questions you might have when implementing Audience Analytics.

## Legal FAQs {#legal}

+++ How do I know if I have Personally Identifiable Information (PII) in my Analytics data? And if yes, what do I do about it?

If you have emails/addresses/etc in a prop or eVar, consider hashing the data during collection. If your country considers IP address to be PII, [turn on IP obfuscation](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html). Talk to your Analytics Admin to see what you are collecting. Talk to your Legal department to see what they consider PII. 

+++

+++ How do I know if my report suites do onsite personalization, or offsite/onsite targeting?

These don't apply to sending Adobe Analytics data to Adobe Audience Manager. Ask yourself: 

* Will you share an Analytics-shared segment with an MCA dimension back to the Experience Cloud? 

* Are you exporting (e.g. via data feeds) out to a Business Intelligence (BI) system that is used for these purposes? 

+++

## Adobe Audience Manager-Specific FAQs {#aam-specific}

+++ How do I create an Analytics destination in Audience Manager?

See [Configure an Analytics Destination in Adobe Audience Manager ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html)". 

+++

+++ After creating and saving an Analytics destination, how long does it take until data appears in my selected report suites?

It can take several hours to populate your report suites with new data.

+++

+++ I've created a new Analytics destination, but I don't see it in the Destination Mappings section of my available segments. Where did that destination go or how do I find it?

An Analytics destination disappears from a segment's Destination Mappings section when you select the **[!UICONTROL Automatically map all current and future segments]** option in **[!UICONTROL Segment Mappings]**. To prevent this, select **[!UICONTROL Manually map segments]** instead of the automatic option. 

+++

Will this give me all of the information from Adobe Audience Manager, in Analytics?

No, only data related to people who come to your site during or after enablement of Audience Manager Audiences and during/after segment qualification. 

+++

+++ Will this give me a per-segment total addressable audience?

Not really. It will tell you the number of visitors in that segment that came to your site during or after segment qualification. 

+++

+++ How is this different from the legacy cookie destination to Analytics?

Segments are qualified for and returned in real time - on the same hit. Friendly names are shown automatically. 

+++

+++ What if some of my report suites have personal data and some do not?<

Tip: Create two destinations - add the personal data report suites to one destination and the non-personal data report suites to the other.

+++

## Analytics-Specific FAQs {#aa-specific}

+++ Will this integration surface as a dimension or segment in Analytics?

As dimensions: Audiences ID and Audiences Name. 

+++

+++Where can I use these dimensions in Analytics?

Everywhere; they are treated just like any other dimension collected in Analytics. 

+++

+++ Why don't I see data coming through in Analytics?

You likely have conflicting Adobe Audience Manager privacy controls between data source and destination. 

+++

+++ Why are some of my segments missing in Analytics, even though I chose to send all segments?<

* Your Adobe Audience Manager data export controls on the destination and in the segments' data sources may be conflicting, preventing certain segments from being sent.

* If you are using 3rd-party data traits in your segments, those segments cannot be shared to destinations (a set of report suites) that contain personal data. 

+++

+++ Why do I see "Audience limit reached" in my Analytics report? (Note: this will also be represented as Audience ID = -1 and "::max_audiences_exceeded::" in Data Warehouse)

By default, the Audience Analytics integration for Adobe Audience Manager sends all segments that a visitor qualifies for, on a per-hit basis, to Analytics. If a visitor belongs to more than 150 Adobe Audience Manager segments on a single hit, the **150 most recently qualified segments** are sent to Analytics, while the remaining list is truncated. An additional flag is sent to Analytics signifying that the segment list was truncated, and displays as "Audience limit reached" in the Audience Name dimension and "-1" in the Audience ID dimension. 

While it is unlikely that a visitor qualifies for more than 150 segments on a particular hit, it may happen a small percentage of the time. If you experience "Audience limit reached" in your reporting, you have two options: 

* Option 1: Continue to let the integration work in its out-of-the-box state, sending the 150 most recently qualified segments for a particular visitor. 

* Option 2: In Adobe Audience Manager, choose the 150 segments that matter most to your business for the integration. Adobe Audience Manager then checks visitors against only those 150 segments. The disadvantage of this approach is that you only receive those 150 segments across all visitors. On the other hand, the Option 1 approach can deliver unlimited segments due to the per-hit nature of the integration. 

+++

+++ Will additional server calls be billed to Analytics for this integration?

No. Adobe Audience Manager Audiences are incorporated into the Analytics hit server-side. This does not incur additional server calls to Analytics (primary or secondary). 

+++

## Server-Side Forwarding (SSF) FAQs {#SSF}

+++ If I have legacy SSF implemented, do I have to also go to Analytics Admin and turn on report suite SSF?

Yes. In the Adobe Audience Manager destination setup, you will see only report suites that have SSF turned on. 

+++

+++ Why can't I turn on certain report suites for SSF in Analytics Admin?

Only suites that are mapped to your Experience Cloud Org can be enabled. 

For more FAQs on this topic, see [Server-Side Forwarding FAQ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md).

+++

## General FAQs {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Why are the segment visitor counts different between Audience Manager and Analytics?

See [Visitor Count Differences](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ What is the difference between "audiences" in Adobe Audience Manager and "segments" in Analytics?

See [Understand Segments in Analytics and Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md). Adobe Audience Manager audiences get sent over and shared as "dimension" components to be used in Analytics. They do not show up as segments in the Segment Builder, for example, but as dimensions that you can build segments with. 

+++

+++ What is the difference between customer attributes and customer data integrated from Adobe Audience Manager?

Customer attributes are not time based; they apply retroactively and go forward. Adobe Audience Manager integrated data is time based and go-forward only. Additionally, customer attributes is a lookup table for Experience Cloud visitor IDs, whereas the Adobe Audience Manager integration is data stitched into each hit for a visitor. 

+++

+++ What about legacy approaches to this problem, for example, the old beta or Consulting plug-in cookie-destinations?

We recommend that you implement the new integration and remove old destinations.

+++
