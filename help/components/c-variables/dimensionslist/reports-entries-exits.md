---
description: The Entry Page report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visits.
seo-description: The Entry Page report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visits.
seo-title: Entries and Exits
solution: Analytics
title: Entries and Exits
topic: Reports
uuid: 756de55b-136b-427b-a80c-f822260131b1
---

# Entries and Exits

>[!NOTE]
>For hits with multiple values in the products variable, Entries and Exits apply to all product values in a hit instead of only the first one.

The Entry Page report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visits.

You can view:

* **Entry Pages** (or sections): Displays, by percentage and by total visits, which pages on your site are the first pages seen by a new visit. You can use this report to identify which of your web pages are the most frequent points of entry, optimize the primary entry points on your site, and drive entry traffic to your key messages.

  A useful way to use the Page View metric is to run a **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Pages Entry]** report, sort by it, and see which entry pages drive the most page views. 

* **Original Entry Pages**: Shows the first page viewed for first-time visitors to your site. Each user is counted only once unless they delete their cookies or are not being tracked with cookies. 
* **Single Page Visits**: Shows pages that are most often both the entry and exit pages for visitor browsing sessions. 
* **Exit Pages**: Displays, by percentage and by total visits, the pages on your site that were the last pages visitors viewed before leaving your site. Exit pages have a visit breakdown scope, meaning they persist across all hits for a visit.

**Metrics on an Entry Pages Report**

* **Entries**: same as instances or occurrences, how many times the specified page is the entry page for a visit. 
* **Visits**: how many visits was this page the entry page, this metric should equal entries. 
* **Exits**: Number of times an Exit occurred where the Entry page was the one specified. If you want to see the number of times the entry page was also the exit page, use the Bounces metric instead of exits.

**Segmentation in an Entry Pages Report**

Running an [!UICONTROL Entry Pages Report] only reports on entry pages, even if you apply segment to a non-entry page.

For example, assume a visit sequence is as follows:

[!DNL Page A] > [!DNL Page B] > [!DNL Page C]

If Page B and Page C are used in a segment, only Page A is reported in an [!UICONTROL Entry Pages Report], because Page A is the entry page. 
