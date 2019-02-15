---
description: Customer Loyalty reveals purchasing patterns of customers.
seo-description: Customer Loyalty reveals purchasing patterns of customers.
seo-title: Customer Loyalty
solution: Analytics
title: Customer Loyalty
topic: Reports
uuid: 7dc30b57-7b18-4228-a6ab-6eb66b3d9402
---

# Customer Loyalty

Customer Loyalty reveals purchasing patterns of customers.

The report displays purchasing patterns of customers based on four categories of loyalty:

* Not a Customer 
* New Customer 
* Return Customer 
* Loyal Customer

Although non-purchase metrics are viewable in this report (such as custom events, shopping cart events, and so on), the categories are always based on the number of orders placed. For example, a visitor might add a custom event named Internal Searches to the report. The [!UICONTROL Return Customer] line item would show the number of internal searches performed by visitors who have made two purchases previously, not the number of visitors who have made two internal searches.

**Customer Loyalty Processing**

The following tables define how Analysis Workspace, Reports & Analytics, Ad Hoc Analysis and Data Warehouse currently process Customer Loyalty: 

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>After May 19, 2016 </p> </th> 
   <th colname="col3" class="entry"> <p>Between April 21 and May 19, 2016 </p> <p>(not applicable to Data Warehouse) </p> </th> 
   <th colname="col4" class="entry"> <p>Before April 21, 2016 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Not a Customer </p> </td> 
   <td colname="col2"> <p>Visitors who have never purchased </p> </td> 
   <td colname="col3"> <p>Visitors who made 0 purchases until the end of a visit. </p> </td> 
   <td colname="col4"> <p>Not available. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>New Customer </p> </td> 
   <td colname="col2"> <p>Visitors who made a single purchase </p> </td> 
   <td colname="col3"> <p>Visitors who made 1 purchase until the end of that visit. </p> <p>(If a purchase happened, the customer status was updated on the next visit after that purchase.) </p> </td> 
   <td colname="col4"> <p>Visitors who made 0 purchases until the end of that visit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Return Customer </p> </td> 
   <td colname="col2"> <p>Visitors who made 2 purchases </p> </td> 
   <td colname="col3"> <p>Visitors who made 2 purchases until the end of the visit where they made 2nd purchase. </p> <p>(If a purchase happened, the customer status was updated on the next visit after that purchase.) </p> </td> 
   <td colname="col4"> <p>Visitors who made 1 purchase until the end of the visit where they made that purchase. </p> <p>(If a purchase happened, the customer status was updated on the next visit after that purchase.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Loyal Customer </p> </td> 
   <td colname="col2"> <p>Visitors who made 3+ purchases </p> </td> 
   <td colname="col3"> <p>Visitors who made 3+ purchases until the end of the visit where they made most recent purchase. </p> <p>(If a purchase happened, the customer status was updated on the next visit after that purchase.) </p> </td> 
   <td colname="col4"> <p>Visitors who made 2+ purchases until the end of the visit where they made most recent purchase. </p> <p>(If a purchase happened, the customer status was updated on the next visit after that purchase.) </p> </td> 
  </tr> 
 </tbody> 
</table>

|  version 14 Customer Loyalty (Current)  |
|---|
|  New Customer  | 1 visit and 1 purchase  |
|  Return Customer  | More than 1 visit and 2 purchases  |
|  Loyal Customer  | More than 1 visit and 3+ purchases  |

The loyalty state changes immediately following the purchase event within the same visit. For example, a New Customer (1 purchase) makes a purchase and then registers for a newsletter after that purchase within the same visit. The newsletter registration event is considered a Return Customer interaction, because the visitor's customer loyalty state changed immediately after the purchase occurred. 
