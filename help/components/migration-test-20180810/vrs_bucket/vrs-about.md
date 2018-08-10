---
description: Virtual report suites segment your Adobe Analytics data so you can control access to each segment.
seo-description: Virtual report suites segment your Adobe Analytics data so you can control access to each segment.
seo-title: Virtual Report Suites
title: Virtual Report Suites
uuid: bec0877c-8339-4861-a5a9-1aa5120f2d94
index: y
internal: n
snippet: y
translate: y
---

# Virtual Report Suites

Many customers have data flowing into a global report suite, but also have data flowing into smaller report suites. They set a variable to multiple report suites, and send their data to more than one report suite. This is referred to as *multisuite tagging*, or *base/parent report suites*. 

For example, all data might be collected in one report suite, but then you can set up secondary report suites so other people in your company have access to part of the data, but not all of it. Data might be divided by region. You might have different websites for different countries. Other examples might be specific brands that belong to a larger company, but that each have their own marketing teams. 

A *virtual report suite* (VRS) allows you to reproduce this branching concept, using segments instead of multiple report suites. Data is sent to one report suite, then is divided according to segments. Using the multiple brands example, you might set a prop for the brand that an item belongs to. Using segments, you can report on the items assigned to each prop. Each of these segments becomes its own view, effectively creating a new report suite. You don't send data specifically to that segment, only to the global report suite, but it functions in your reports as if it were a different report suite. 

A virtual report suite inherits most of the service levels of the base report suite, such as eVar settings, Processing Rules, Classifications, etc. The following settings are NOT inherited: 


* Report suite ID (RSID)
* Report suite name
* Permission groups (virtual report suites can be assigned to their own permission groups)


## Benefits of Virtual Report Suites {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Customers pay for secondary server calls, so eliminating these calls can result in significant savings. A virtual report suite is also completely retroactive. If the global report suite already contains data, the relevant data is automatically included in a new virtual report suite. A new secondary report suite would only begin collecting data after it is created, so it would not include any historical data. When you implement Analytics, you only need to send data to one report suite, rather than having to create implementations for the global report suite and each secondary report suite. 

Virtual report suites help: 


* Simplify implementation by allowing you to use a single Report Suite ID (RSID) across all sites/domains. Having all data in a single report suite enables customer analytics as we move toward the next generation of Adobe Analytics.
* Business users in your organization always see only the data segments that are relevant to them.
* Improve security by allowing Admin users to control data access more easily and more granularly after implementation.
* Provide the ability to participate in Device Co-op
* People metric
* A single-customer view of data (in the future)
* The ability to create unlimited virtual report suites to segment out data


## Limitations of Virtual Report Suites {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Virtual report suites have the following limitations: 


* Any limitations of segments apply to virtual report suites A virtual report suite is nothing more than a segment applied to a report suite. Because each report suite has its own data warehouse and its own data feed, using multiple report suites results in some benefits that segments do not provide. 

* Real-time report
* Settings and variable names can't be customized like in a full report suite


## Virtual Report Suites vs. Multisuite Tagging {#section_317E4D21CCD74BC38166D2F57D214F78}



<table id="table_9031118A5F79494698FD824F2B3C0EC9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Capability </p> </th> 
   <th colname="col2" class="entry"> <p>Virtual Report Suite </p> </th> 
   <th colname="col3" class="entry"> <p>Multisuite Tagging </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Offers real-time or "Current Data" reporting </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Works in all Analytics Tools (Analysis Workspace, Report Builder, Ad Hoc Analysis, etc.) </p> </td> 
   <td colname="col2"> <p>Yes </p> <p> <p>Note:  You can edit and identify them as virtual report suites only in Reports &amp;amp; Analytics. However, you can select them in report suite drop-downs in the other tools. </p> </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can upload data to it (via classifications, data feeds, etc.) </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supports creation of DL Reports, bookmarks, dashboards, targets, alerts, segments, calculated metrics... </p> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can be individually added to Permissions Groups </p> </td> 
   <td colname="col2"> <p>Yes </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Can use Admin functions to modify individual settings on this report suite (Admin &amp;gt; Report Suites) </p> </td> 
   <td colname="col2"> <p>No (Settings are inherited from parent) </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
  </tr> 
 </tbody> 
</table>


## Combining Virtual Report Suites and Multisuite Tagging {#section_026FA3FCD7314DD18220E73EC5702AFF}

In some cases, there are benefits to using both virtual report suites and multisuite tagging. 

For example, a retailer might use a report suite for each brand, and virtual report suites for each brand to break data out by region. Similarly, an athletic organization might use a report suite for each team, then virtual report suites to divide fans in the team's region from those outside the region. 
