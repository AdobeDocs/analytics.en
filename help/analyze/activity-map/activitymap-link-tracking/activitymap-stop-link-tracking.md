---
description: Steps for stopping link tracking in Activity Map or Legacy ClickMap.
title: Stop link tracking
uuid: e17fb7bd-d6ed-45c3-a006-9150d5718cff
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: cdbec360-bff9-452c-9564-6b481e7175d3
---
# Stop link tracking

Steps for stopping link tracking in Activity Map or Legacy ClickMap.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> To stop link tracking in... </th> 
   <th colname="col2" class="entry"> Do this... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Remove the following content from the Appmeasurement.js file: 
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://experienceleague.adobe.com/docs/ analytics/analyze/activity-map/getting-started/get-started-admins/activitymap-enable.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (formerly Visitor ClickMap) </td> 
   <td colname="col2"> <p>Set the <a href="https://experienceleague.adobe.com/docs/ analytics/implementation/vars/config-vars/configuration-variables.html"  > trackInlineStats</a> variable to false (this is the default.) The syntax reads as follows: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>
