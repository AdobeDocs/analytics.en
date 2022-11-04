---
description: Adobe requires advance notice for new account setups, traffic spikes and traffic increases. Hardware must be allocated in advance to minimize latency and possible adverse impacts to the overall system.
title: Required lead time for traffic increases
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
---
# Required lead time for traffic increases

Adobe requires advance notice for new account setups, traffic spikes and traffic increases. Hardware must be allocated in advance to minimize latency and possible adverse impacts to the overall system.

Allocation of hardware is driven by alerts submitted through the reports & analytics user interface.

>[!IMPORTANT]
>
>Adobe cannot accommodate "placeholder" traffic change requests. Unless otherwise indicated, adhere to the suggested lead time as closely as possible, including not sending an alert too early. See [Schedule a traffic spike](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) or [Specify permanent traffic increase](/help/admin/c-traffic-management/t-traffic-permanent.md).

Use the following guidelines to determine how far in advance you must submit a traffic alert:

## Hardware Allocation Lead Times


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Traffic Notification </th>
   <th colname="col2" class="entry"> <p>Lead Time Needed </p> </th>
   <th colname="col3" class="entry"> <p>Notes </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> New report suite creation </td>
   <td colname="col2"> 5 business days </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> X </td>
   <td colname="col2"> X </td>
   <td colname="col3" morerows="3"> X </td>
  </tr>
  <tr>
   <td colname="col1">Y </td>
   <td colname="col2"> Y </td>
  </tr>
  <tr>
   <td colname="col1"> Z </td>
   <td colname="col2"> Z </td>
  </tr>
  <tr>
   <td colname="col1"> <p> Z </p> </td>
   <td colname="col2"> Z </td>
  </tr>
 </tbody>
</table>

Other things to consider:

* If you have several report suites starting up or increasing that add up to the numbers listed above, the lead time applies as a sum of the traffic expected for each of them.
* Have the following information available to submit a traffic change:

  * Report suite ID
  * Estimated hits per day
  * Go-live date

* Client Alerts are also needed when traffic decreases or a report suite is deprecated.

## Hardware De-Allocation Due to Unrealized Traffic

Hardware for new accounts, traffic spikes and traffic increases will be de-allocated if the projected traffic in the client alert does not materialize within 4 weeks of the "Go live date". If the traffic is still anticipated, a new client alert must be generated as a traffic increase.
