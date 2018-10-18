---
description: Virtual report suites can be used to replace multi-suite tagging. For example, instead of sending data to two separate report suites, you could send data to one and use virtual report suites to limit how much data users have access to. However, access to data is only one of the reasons that separate report suites can be beneficial. Carefully consider the following use cases before making implementation changes with regard to virtual report suites.
keywords: Virtual Report Suite
seo-description: Virtual report suites can be used to replace multi-suite tagging. For example, instead of sending data to two separate report suites, you could send data to one and use virtual report suites to limit how much data users have access to. However, access to data is only one of the reasons that separate report suites can be beneficial. Carefully consider the following use cases before making implementation changes with regard to virtual report suites.
seo-title: VRSs and global/multi-suite tagging considerations
solution: Analytics
title: VRSs and global/multi-suite tagging considerations
topic: Reports and analytics
uuid: 79c01a24-b2f4-4c6a-9c24-eb01a0c1dc09
index: y
internal: n
snippet: y
---

# VRSs and global/multi-suite tagging considerations

Virtual report suites can be used to replace multi-suite tagging. For example, instead of sending data to two separate report suites, you could send data to one and use virtual report suites to limit how much data users have access to. However, access to data is only one of the reasons that separate report suites can be beneficial. Carefully consider the following use cases before making implementation changes with regard to virtual report suites.

>[!IMPORTANT]
>
>After you have read through the considerations below and have decided to remove secondary server calls and use virtual report suites instead, here is what you need to do: 
>
>1. Create virtual report suites to match the data in your secondary/child report suites. 
>
>    * Use the virtual report suites to test against your secondary report suites to make sure the data looks good. 
>    * Adjust the segments that the virtual report suites are based on, as necessary. 
>    * As a best practice, use segment stacking wherever possible so you can edit a segment in one location and have it apply to all virtual report suites that use that segment. For example, if I want to build one VRS for "mobile users from Europe," and another one for "mobile users from Asia," create one segment for mobile users and then separate segments for European and Asian users. This way, if you want to update the definition of your "mobile users" segment, you can do so in a single segment without needing to update each virtual report suite segment individually. 
>    * If you are looking for mutually exclusive data sets in your virtual report suites (for example, you want to see "Domain A" and "Domain B" as separate report suites, and you do not want any of Domain A's traffic in Domain B's report suite, use a "hit" container for your segments. 
>
>1. After you confirm that the virtual report suites you created are set up correctly and will meet your team's needs, remove the secondary report suite IDs from your implementation. Leave only your global/parent report suite IDs to collect data from your sites and apps. 
>
>   If you are unable to edit your implementation, work with your Adobe account team. They can explore options for preventing your secondary server calls from being processed by Adobe Analytics. 
>

The following considerations apply ONLY to cases where you are considering changing your implementation to remove child report suites and rely solely on virtual report suites to control views into data for end users. None of the following considerations apply to normal use of virtual report suites as a way to segment existing report suites and make that data available to users (without dramatically altering your underlying implementation).

## Users at your company need to be able to share segments to the Experience Cloud for targeting from virtual report suites. {#section_42BC8FB63E3444E3893913C43D19D032}

**Use case**: Users have access to virtual report suites only, but you want them to be able to create and share segments from Adobe Analytics to Adobe Experience Cloud for targeting in Adobe Target.

* Sharing segments to Adobe Experience Cloud is not supported for virtual report suites. 
* Users who need to be able to share a segment to Experience Cloud must have access to the global/parent report suite.

## You don't need real-time (or "Current Data") reporting at the virtual report suite level. {#section_3EEF63BBBC934B81B01A1FD2CC91D704}

* The real-time report is not supported in virtual report suites, because the data is segmented. 
* The same is true of the "Current Data" setting.

**Use case**: You are setting up virtual report suites for each of your properties, but each property has a newsroom that relies on the real-time report. You should use secondary server calls.

## You do not exceed unique value limits in your "base" (parent) report suites. {#section_3DB21E5F4E2749298F40CDD096EE28AF}

Or: You do not care if your users see "Low Traffic" in their virtual report suites.

** Use case**: You have millions of page names in your global report suite, and you want to be sure that you see every single unique page name in your child suites. You should use secondary server calls.

## You do not need different variable definitions and mappings for each individual "child" report suite. {#section_CD8D7A9A496844EF9E45C945BFADCC96}

* For example, you do not get a separate bank of eVars for each virtual report suite; each one uses the same eVar naming and definition as the base report suite. 
* The same applies to Marketing Channels.

**Use case**: The first 50 eVars in your global suite are common to all of your different brands that roll up into it, but the next 50 are unique and different to each brand. You should use secondary server calls.

## The segments you are going to use with virtual report suites do not divide the data in ways that may confuse your users. {#section_FD25B3181C5E4ECA8EC5D7D600391DCD}

Remember that a virtual report suite is just a segment applied to a report suite; all nuances in segmented data apply.

**Use case 1**: Your virtual report suite is based on a segment defined as "all shopping cart hits". Running pathing reports would show shopping cart pages as the start of the visit, since all hits prior to the shopping cart are excluded. You may want to use secondary server calls, depending on your needs.

**Use case 2**: You have five sites. Your users want to see Visit Number data on a per-site basis, meaning that they want to see the number of first visits, second visits, etc. at a site level.

With a global suite, visit number is typically aggregated across all sites (Visit #1 can be to SiteA, Visit #2 can be to SiteB, and so on). When using a Virtual Report Suite to segment by site (for example, All SiteB visits), the visit number corresponds to the selected site. In the example just given, a virtual report suite for all SiteB visits would show zero for Visit #1, because Visit #1 happened on SiteA. If this is concerning, you should use secondary server calls.

## You have no problem with Adobe Analytics converting various currencies at report run time. {#section_D5A797633E7D4EA7B9B3A147E260B3AF}

* Virtual report suites do not convert revenue from one currency to another like regular report suites do. 
* Adobe Analytics does allow you to convert currency when running reports but the exchange rate is based on the current day, even for historical data.

**Use case**: You do business in several countries and each country wants to view historical revenue data in their own currency with an accurate historical exchange rate. You should use secondary server calls.

## Your company's usage of Adobe Analytics for querying is not extreme. {#section_27831ACB93AC450384F4533BE7FB5F0D}

* Running tens of thousands of data queries (reports, Report Builder data blocks, API calls, etc.) against a single report suite concurrently can impact performance. 
* Using separate report suite allows you to parallelize your queries. 
* This also applies to classifications uploads, which can take longer on a single massive report suite.

**Use case**: You have a thousand Report Builder dashboards, each with 50 data blocks, that are scheduled to run at the same time every Monday morning. You should use secondary server calls.

## You are okay with getting a single Data Feed that includes all of your data. {#section_57E4ECEF6B774A868F3C8BBD5E919901}

* You cannot do Data Feeds for virtual report suites.

**Use case**: You want to push a Data Feed for Brand A to that team every night for them to use, without having to first segment/ETL a global Data Feed for all of your brands in order to get their data and send it over to them. You should use secondary server calls.

## You are using an Exchange (data connectors) integration that only allows one partner account per report suite, and you have multiple partner accounts that you want to integrate. {#section_5F58D01B43834D58BD1017CFF8A3EB71}

* For example, you can only have one DFA account integrated per report suite. 
* You cannot set up Exchange integrations on a per-virtual-report-suite basis. 
* Check with the specific Exchange integrations that you want before you consolidate down to a single parent report suite.

**Use case**: Each of your regional teams has its own DFA account and wants to integrate pre-click display ad data into their report suites. You should use secondary server calls.

## Other consideration: Localization in different report suites (e.g., each language referring to the same product differently) {#section_47A7C2C3624249DEAE5F54C62B7E5EF6}

* In the global suite, these localized product names, page names, and so on are mixed in their respective reports. 
* If you segment properly by language or geo, the virtual report suites should only contain the correct localized values.

## Other consideration: Multiple visitor counting methodologies (FPC vs. third-party) {#section_9D6C7987613744AD96B91D9D78D6FAE5}

* Consolidating down to a global report suite means that all of your properties should use the same visitor counting methodology (first-party cookies, third-party cookies, Experience Cloud ID, and so on). 
* Continue to use separate report suites for each brand or property if you cannot ensure that all properties can rely on the same methodology.

