---
description: Adobe requires advance notice for new account setups, traffic spikes and traffic increases. Hardware must be allocated in advance to minimize latency and possible adverse impacts to the overall system.
seo-description: Adobe requires advance notice for new account setups, traffic spikes and traffic increases. Hardware must be allocated in advance to minimize latency and possible adverse impacts to the overall system.
seo-title: Required lead time for traffic increases
solution: Analytics
title: Required lead time for traffic increases
topic: Admin tools
uuid: 70b29254-161c-4eb4-b195-4fdd8820fa81
index: y
internal: n
snippet: y
---

# Required lead time for traffic increases

Adobe requires advance notice for new account setups, traffic spikes and traffic increases. Hardware must be allocated in advance to minimize latency and possible adverse impacts to the overall system.

Allocation of hardware is driven by alerts submitted through the reports & analytics user interface. **Unfortunately, Adobe is not able to accommodate “placeholder” traffic change requests. Unless otherwise indicated, please adhere to the suggested lead time as closely as possible, including not sending an alert too early.** (See [Schedule a traffic spike](../c_traffic_management/t_traffic_schedule_spike.md#task_66E0967F49CF49CC9D88CDF517398FAE) or [Specify permanent traffic increase](../c_traffic_management/t_traffic_permanent.md#task_1B3BF0AE020F4936B689D9ED1736FCFF)).

Use the following guidelines to determine how far in advance you must submit a traffic alert:

## Hardware Allocation Lead Times {#section_DA62ED50BD604963A4BDB1D601A94838}

<table id="table_A67CC3B164F740088797BD8913244E47"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DAILY Traffic Estimates (Hits) </th> 
   <th colname="col2" class="entry"> <p>Lead Time Needed (January - October) </p> </th> 
   <th colname="col3" class="entry"> <p>Lead Time Needed (November - December) </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Up to 1,000,000 </td> 
   <td colname="col2"> No lead time needed </td> 
   <td colname="col3"> No lead time needed </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1,000,000 - 5,000,000 </td> 
   <td colname="col2"> Two BUSINESS days </td> 
   <td colname="col3" morerows="3"> All traffic increases targeted for November-December should be submitted by September 15th. This is to allow time to purchase capacity if necessary to accommodate holiday traffic. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5,000,000 - 10,000,000 </td> 
   <td colname="col2"> One calendar week </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 10,000,000 - 25,000,000 </td> 
   <td colname="col2"> Two calendar weeks </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Above 25,000,000 </p> </td> 
   <td colname="col2"> One or more months </td> 
  </tr> 
 </tbody> 
</table>

Other things to consider:

* If you have several report suites starting up or increasing that add up to the numbers listed above, the lead time applies as a sum of the traffic expected for each of them. 
* Have the following information available to submit a traffic change:

    * Report suite ID 
    * Estimated hits per day 
    * Go-live date

* Client Alerts are also needed when traffic decreases are or a report suite is deprecated.

## Hardware De-Allocation Due to Unrealized Traffic {#section_9C5BA8E7D85E4B33BCD78D8CC3C94E2A}

Hardware for new accounts, traffic spikes and traffic increases will be de-allocated if the projected traffic in the client alert does not materialize within 4 weeks of the “Go live date”. If the traffic is still anticipated, a new client alert must be generated as a traffic increase. 
