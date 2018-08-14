---
description: Steps for stopping link tracking in Activity Map or Legacy ClickMap.
seo-description: Steps for stopping link tracking in Activity Map or Legacy ClickMap.
seo-title: Stop link tracking
solution: Analytics
title: Stop link tracking
topic: Activity map
uuid: 8f4b010d-6a11-4524-a305-20e9f6972818
index: y
internal: n
snippet: y
translate: y
---

# Stop link tracking


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
    <codeblock>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE
     
     &nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (formerly Visitor ClickMap) </td> 
   <td colname="col2"> <p>Set the <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external"> trackInlineStats</a> variable to false (this is the default.) The syntax reads as follows: 
     <codeblock>
       s.trackInlineStats=false
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

