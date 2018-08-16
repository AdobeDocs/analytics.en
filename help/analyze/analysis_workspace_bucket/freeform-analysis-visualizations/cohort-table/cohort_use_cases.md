---
description: Use case examples for cohort analysis.
keywords: Analysis Workspace
seo-description: Use case examples for cohort analysis.
seo-title: Cohort analysis use cases
solution: Analytics
title: Cohort analysis use cases
topic: Reports and analytics
uuid: f42bf40d-240f-4459-aacf-b4152aef54d9
index: y
internal: n
snippet: y
translate: y
---

# Cohort analysis use cases


## App engagement use case {#section_ADEC6EE79F1846319B2E0D9544CC5E40}

Suppose that you want to analyze how users who install your app engage with it over time. Do they install it and never use it? Do they use it for a while, then fall away? Or do they remain engaged over time? 

You can create a six-month cohort analysis 

**Granularity**: Monthly, from January 2015 through June 2015. 

**Inclusion metric**: App Installs. 

**Return metric**: Sessions or Launches 

Visitors do not count as *` engaged`* in subsequent months unless they are having a session or at least launching the app. Cohort analysis would then show you patterns in usage where *` App Install`* always occurs on Month 0. You might notice that usage dips in Month 2, regardless of when users installed the app. (For those who installed the app in January 2015, Month 2 is March 2015. For those who installed the app in February 2015, Month 2 is April 2015, and so on.) This analysis allows you send an email or a push message to all users during the second month after they install the app to remind them to use the app. 

## Subscription use case {#section_FDECB16766CF415BB84AE46BA491FB5F}

You work at Adobe.com and offer a free Creative Cloud subscription. The goal is for users to upgrade from the free version to the 30-day trial version or, ultimately, the paid version. 

**Granularity**: Monthly 

**Inclusion metric**: Download Link 

**Return metric**: Purchase Paid Creative Cloud 

Using this cohort analysis, you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. 12-15% upgrade in the second month of use. After that, upgrading significantly drops off: 4-5% in month three, 3-4% in month four, and 1-2% in month five. 

Recognizing that you need to not lose potential customers in month three, you set up an email campaign designed to go out in the middle of month three to a sample of users, offering a $50 coupon to users who have not yet upgraded. 

Check back with your cohort analysis report a few months later. For cohorts formed after the launch of the campaign, conversion to paid Creative Cloud subscriptions in month three has risen from 4-5% to 13-14%, resulting in hundreds of thousands of dollars per cohort, for every monthly cohort that hits month three from that point forward. 
