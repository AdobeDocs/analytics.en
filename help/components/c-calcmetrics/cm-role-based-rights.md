---
description: Calculated metrics rights differs between Admin-level users and non-Admins.
title: Calculated metrics  role-based rights
uuid: 7c14d32d-370c-4afa-8f80-5bbd8fc12ec7
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
---
# Calculated metrics: role-based rights

Calculated metrics rights differs between Admin-level users and non-Admins.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Create </th> 
   <th colname="col2" class="entry"> Share </th> 
   <th colname="col3" class="entry"> View/Manage </th> 
   <th colname="col4" class="entry"> Approve </th> 
   <th colname="col5" class="entry"> Apply </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Admin-level users</b> </td> 
   <td colname="col02"> Admins can create calculated metrics as well as create <a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html"  > groups </a> to limit the rights of users to create calculated metrics. </td> 
   <td colname="col2"> Can share with entire company, with user groups, and with individual users. </td> 
   <td colname="col3"> <span class="keyword"> Reports & Analytics</span>: Can view/edit/delete/etc. their own and other users' calculated metrics. <p> <span class="keyword"> Report Builder </span>: Can view/edit/delete/etc. its own calculated metrics and those shared with it. </p> </td> 
   <td colname="col4"> Can approve calculated metrics as canonical. </td> 
   <td colname="col5"> Can apply any calculated metrics across the whole organization. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Non-Admin-level users</b> </td> 
   <td colname="col02"> By default, users can create calculated metrics. However, these rights may be limited by Administrators. </td> 
   <td colname="col2"> Can share with individual users only </td> 
   <td colname="col3"> Can view/edit/delete/etc. only their own calculated metrics. <p>Non-admin users must have access to all the component events to be able to see a shared metrics (the permissions in the Admin console are still enforced). </p> <p>If a dashboard or scheduled report is shared with a non-admin user and they don't have the metric shared with them, the report will run with the metric applied (assuming they have permissions to view the events). However, they will not be able to see the definition or edit the metric. </p> </td> 
   <td colname="col4"> Can only consume approved calculated metrics; cannot mark as approved. </td> 
   <td colname="col5"> Can apply their own calculated metrics and segments that have been shared with them. </td> 
  </tr> 
 </tbody> 
</table>
