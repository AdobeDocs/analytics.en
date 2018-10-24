---
description: Displays information regarding visitors, including things like visitor count, customer loyalty, and visitor characteristics.
seo-description: Displays information regarding visitors, including things like visitor count, customer loyalty, and visitor characteristics.
seo-title: Visitor reports
solution: Analytics
title: Visitor reports
topic: Ad hoc analysis
uuid: 49e1af84-11a4-4d83-87db-95494b139784
index: y
internal: n
snippet: y
---

# Visitor reports

Displays information regarding visitors, including things like visitor count, customer loyalty, and visitor characteristics.

## Return Frequency {#concept_447A99B71E484D27A7A02888CC51FD3D}

Shows the length of time that passes between visits from returning visitors, and the number of visits that fall into each time length category. Use the report to see the average amount of time that repeat visitors go without visiting your site, and the trends in repeat customers.

<!-- 

c_reports_return_freq.xml

 -->

For example, showing the Orders metric in this report helps a retail site understand the most effective time between visits in generating conversion. Use this information to market effectively to visitors who have gone a certain period of time without visiting your site.

You can:

* Identify the number of return visitors and the frequency of their return visits. 
* Evaluate your website's appeal and relevance to visitors over time. 
* Know how sticky your site is to visitors and how often they feel compelled to return for further interaction or updates. 
* Identify the impact of your website's content and promotions on your visitors.

By default, this report has the following time lengths:

* Less than one day 
* One to three days 
* Three to seven days 
* Seven to fourteen days 
* Fourteen days to one month 
* Longer than one month

## Visit Number {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Shows which customer visit numbers on your site most influenced your success metrics. A visitor making a first visit to your site is counted in the Visit Number 1 line item. Visitors that return to the site for a second visit are counted in the Visit Number 2 line item, and so forth.

<!-- 

c_reports_visit_number.xml

 -->

You can use this report as a fallout report to see whether visitors are returning. You can also add a revenue metric to see whether you generate more revenue from initial visits or subsequent visits.

For example, this report could answer questions such as: Did customers who purchased on their fourth visit generate more revenue than those who purchased on their first visit?

You can break down this report by any other report or variable to determine:

* How many visits does it typically take a user who clicked through campaign XYZ to make a purchase. 
* Whether users in Tokyo, for example, make more visits before generating a lead than users in London.

>[!NOTE]
>
>If the same visitor visits your website multiple times in the same period, each specified visit number is incremented for each visit.

This report is based on the visitor ID data that is passed to Adobe on every hit made by visitors. As this data is received, Adobe compares it to historical visitor ID data to determine whether the hit is:

* A new visitor (Visit Number equals 1). 
* A previous visitor continuing a visit (Visit Number is not incremented). 
* A previous visitor making a new visit (Visit Number is incremented by one).

>[!NOTE]
>
>Each Analytics visitor ID is associated with a visitor profile on Adobe servers. Visitor profiles are deleted after at least 13 months of inactivity regardless of any visitor ID cookie expiration.

## Customer Loyalty {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Use this report to see whether your revenue is most affected by new customers or by repeat customers.

<!-- 

c_reports_customerloyalty.xml

 -->

The [!UICONTROL Customer Loyalty] report displays purchasing patterns of customers based on four categories of loyalty:

* **Not a Customer**: Visitors that have never purchased 
* **New Customer**: Visitors that made a single purchase 
* **Return Customer**: Visitors that made 2 purchases 
* **Loyal Customer**:Visitors that made 3+ purchases

>[!NOTE]
>
>When using these metrics, all user Visits (or all Visitors) are represented in this report, regardless of whether the Visit (or Visitor) included a purchase.

The loyalty state changes after the end of the visit where a purchase event occurs. For example, a New Customer (1 purchase) makes a purchase and then registers for a newsletter after that purchase within the same visit. The newsletter registration event is still considered a New Customer interaction, because the visitor’s Customer Loyalty state will not change until the next visit. 

## Visitor Profile {#concept_4D829198CD144DCDA667E0651F93AFC7}

Displays information about the type of visitor that comes to your site. You can see things like location of the visitor, the type of browsers and computer hardware used, languages used, and Internet service provider data for your visitors.

<!-- 

c_reports_visitor_profile.xml

 -->

** [!UICONTROL Languages] **: Displays your visitors’ preferred languages, captures the default browser language, and displays the languages that visitors use most often on your site.

** [!UICONTROL Domains] **: Lists the organizations and ISPs your visitors use to access your site. This report differs from the [!UICONTROL Full Domains] report in that the Full Domains report registers the full ISP domain, whereas this report lists the secondary domain.

** [!UICONTROL Top Level Domains] **: Identifies world regions that visitors come from based on their originating domain extension, and shows how many visitors come from these countries. Domains ending in Commercial (.com), Network (.net), Education (.edu), Government (.gov) and Organization (.org) are usually based in the United States, and are listed separately from the rest of the domains.

** [!UICONTROL Visitor ZIP/Postal Code] **: Displays the zip and postal codes that produced the customers that had the greatest effect on purchase success metrics. 

## GeoSegmentation {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Shows the geographic dynamics of your visitors in real-time, including the countries, states and cities from which they are browsing. You can also gain important insights into the technology and preferences of your website's audience. 
