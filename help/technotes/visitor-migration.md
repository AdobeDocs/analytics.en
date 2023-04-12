---
description: Visitor migration is a process where the visitor ID cookie is migrated from one domain to another.
keywords: Analytics Implementation
title: Visitor migration
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
---
# Visitor migration

>[!NOTE]
>
>If you have already implemented Experience Cloud Visitor ID Service then Grace Period is not applicable for you and should not be enabled. 

Visitor migration is a process where the visitor ID cookie(s_vi) is migrated from one domain to another.

Visitor migration lets you preserve visitor identification cookies when changing data collection domains. Data collection domains might change for the following reasons:

* Moving from `2o7.net` to `adobedc.net`.

* You are implementing the [Experience Cloud Visitor ID Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) and are moving from a CNAME/first-party data collection domain to `adobedc.net`, `2o7.net` or `omtrdc.net`

* Moving to a cname/first-party data collection ( [First-Party Cookies)](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

* Moving from one CNAME to another (changing domains).

After visitor migration is configured, when a user visits the new domain without a visitor ID cookie, the server redirects to the previous data collection hostname, retrieves any available visitor ID cookies, and then redirects back to the new domain. If a Visitor ID is not found on the previous hostname, a new ID is generated. This occurs only once per visitor.

## Visitor Migration Process {#section_FF0C5C5CAEF343FFA1892B29311F7160}

The following table lists the tasks required for visitor migration: 

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>To get started:</b> <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"  > Contact Customer Care </a> with the domain(s) you want to migrate, and the migration period you would like to enable (30, 60, or 90 days). Make sure that you include the non-secure and secure domains. </p> </td> 
   <td colname="col3"> <p>Create a list with the <i>exact</i> syntax for the domains you want to migrate to and migrate from. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>The migration host names are configured on Adobe Data collection server. Customer Care will let you know when the change is made so you can plan for the next step. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6+ hours after configuration change</b>: Update the <code> s.trackingServer</code> and <code> s.trackingServerSecure</code> variables in your Analytics JavaScript code to use the new data collection servers. </p> </td> 
   <td colname="col3"> <p>After you make this change, use the <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html"> Experience Cloud debugger</a> to verify that the Analytics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immediately after updating your Analytics code</b>: Test your site to verify that the redirect to the previous data collection domain is occurring. </p> </td> 
   <td colname="col3"> <p>Use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that when you access your site for the first time, or after clearing cookies, you see two 302 (redirect) HTTP status codes before the 200 (OK) HTTP status code. If any of these redirects fail, contact Customer Care immediately to ensure that the migration is configured correctly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>For the entire migration period</b>: Keep the DNS record for the previous hostname active. </p> </td> 
   <td colname="col3"> <p>The previous hostname must resolve through DNS or the cookie migration will not occur. </p> </td> 
  </tr> 
 </tbody> 
</table>
