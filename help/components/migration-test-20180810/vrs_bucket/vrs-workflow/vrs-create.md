---
description: Before you start creating virtual report suites, here are a few things to keep in mind.
keywords: Virtual Report Suite
seo-description: Before you start creating virtual report suites, here are a few things to keep in mind.
seo-title: Creating Virtual Report Suites
solution: Analytics
title: Creating Virtual Report Suites
topic: Reports and analytics
uuid: 8ba50810-7793-41a9-bda0-486d7572ae9a
index: y
internal: n
snippet: y
translate: y
---

# Creating Virtual Report Suites


* Non-Admin users cannot see the Virtual Report Suite Manager.
* Virtual report suites cannot be shared. "Sharing" is done via groups/permissions.
* In the Virtual Report Suite Manager, you can see only your own virtual report suites. You have to click “show all” to see everyone else’s.

1. Navigate to ** [!UICONTROL  Components] ** > ** [!UICONTROL  Virtual Report Suites] **.
1. Click ** [!UICONTROL  Add +] **. ![](graphics/new_vrs.png) 

1. Fill in the fields:

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> <p>The name of the virtual report suite is not inherited from the parent report suite and should be distinct. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Description </td> 
   <td colname="col2"> <p>Add a good description for the benefit of your business users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tags </td> 
   <td colname="col2"> <p>You can add tags to organize your report suites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groups </td> 
   <td colname="col2"> <p>Select the permission groups that you want to have access to this VRS. (You can also manage group permissions from 
     <ignoretag>
      <span class="uicontrol"> Admin</span> &gt; 
      <span class="uicontrol"> User Management</span> &gt; 
      <span class="uicontrol"> Groups</span>
     </ignoretag>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent Report Suite </td> 
   <td colname="col2"> <p>The report suite from which this virtual report suite inherits the following settings. Most service levels and features (for example, eVar settings, Processing Rules, Classifications, and so on) are inherited. To make a changes to these inherited settings on a VRS, you must edit the parent report suite (
     <ignoretag>
      <span class="uicontrol"> Admin</span> &gt; 
      <span class="uicontrol"> Report Suites</span>
     </ignoretag>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time zone </td> 
   <td colname="col2"> <p>Choosing a time zone is optional. </p> <p>If you choose a time zone, it is saved along with the VRS. If you do not choose one, the time zone of the parent report suite is used. </p> <p>When editing a VRS, the time zone saved with the VRS appears in the drop-down selector. If the VRS was created before time zone support was added, the parent report suite's time zone is shown in the drop-down selector. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segments </td> 
   <td colname="col2"> <p>You can add just one segment or you can <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_stack.html" format="https" scope="external"> stack segments</a>. </p> <p> <p>Note:  When stacking two segments, they are joined by an AND statement. This cannot be changed to an OR statement. </p> </p> <p>When you try to delete or modify a segment that is currently used in a virtual report suite, a warning displays. </p> </td> 
  </tr> 
 </tbody> 
</table>

