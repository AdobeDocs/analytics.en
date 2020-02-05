---
description: Visitor migration is a process where the visitor ID cookie is migrated from one domain to another.
keywords: Analytics Implementation
title: Visitor migration
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
---

# Visitor migration

Visitor migration is a process where the visitor ID cookie is migrated from one domain to another.

Visitor migration lets you preserve visitor identification cookies when changing data collection domains. Data collection domains might change for the following reasons:

* Moving from `2o7.net` to `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)).

* You are implementing the [Experience Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) and are moving from a CNAME/first-party data collection domain to `2o7.net` or `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)) 

* Moving from `2o7.net` or `omtrdc.net` to a cname/first-party data collection ( [First-Party Cookies)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/).

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
   <td colname="col1"> <p> <b>To get started:</b> <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"  > Contact Customer Care </a> with the domain(s) you want to migrate, and the migration period you would like to enable (30, 60, or 90 days). Make sure you include the non-secure and secure domains. </p> </td> 
   <td colname="col3"> <p>Create a list with the <i>exact</i> syntax for the domains you want to migrate to and migrate from. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>The migration host names are configured on Adobe Data collection server. Customer Care will let you know when the change is made so you can plan for the next step. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6+ hours after configuration change</b>: Update the <code> s.trackingServer</code> and <code> s.trackingServerSecure</code> variables in your Analytics JavaScript code to use the new data collection servers. </p> </td> 
   <td colname="col3"> <p>After you make this change, use a [packet monitor](../implement/validate/packet-monitor.md) to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immediately after updating your Analytics code</b>: Test your site to verify that the redirect to the previous data collection domain is occurring. </p> </td> 
   <td colname="col3"> <p>Use a [packet monitor](../implement/validate/packet-monitor.md) to verify that when you access your site for the first time, or after clearing cookies, you see two 302 (redirect) HTTP status codes before the 200 (OK) HTTP status code. If any of these redirects fail, contact Customer Care immediately to ensure that the migration is configured correctly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>For the entire migration period</b>: Keep the DNS record for the previous hostname active. </p> </td> 
   <td colname="col3"> <p>The previous hostname must resolve through DNS or the cookie migration will not occur. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Deprecated visitorMigrationKey and visitorMigrationServer Variables {#section_32FCEE2575944D039EA0FEBFB5814259}

As of March 2013, the `visitorMigrationKey`, `visitorMigrationServer`, and `visitorMigrationServerSecure` data collection variables are deprecated and no longer used. The data previously contained in these variables are now stored on Adobe servers for increased security.
