---
description: The Data Governance dialog in the Admin Tools provides an overview of which report suites have been configured for data governance, whether they have been mapped to an Experience Cloud organization, and whether a data retention policy is in place for this report suite.
title: View/Manage Report Suite's Data Governance Settings
uuid: f3b83e8e-00af-4a60-a5de-29b5c43f6788
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
---
# View/Manage Report Suite's Data Governance Settings

The Data Governance dialog in the Admin Tools provides an overview of which report suites have been configured for data governance, whether they have been mapped to an Experience Cloud organization, and whether a data retention policy is in place for this report suite.

1. Log in to Adobe Experience Cloud.
1. Navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]**.

   You will see all the report suites that are part of your login company:

   ![](assets/privacy_setup_an.png)

<table id="table_448292730FF0475E9DCB731882F9A29B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Report Suites </p> </td> 
   <td colname="col2"> <p>The first line lists the friendly name of the report suite. The second line contains the internal name of the report suite. If you are allowed to set labels for a report suite, the first line will be a clickable link that takes you to the labeling page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organization Mapping </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EF8F613B0C5E42D19DB60BD0C89C114B"> 
     <li id="li_B35EE88555F547EFBF55ADE9D0C9EC3B"><b>Mapped</b>: This report suite has already been mapped to the same Experience Cloud organization as the Analytics login company that you are logged in to. Only report suites that have this setting can be labeled. </li>
     <li id="li_FF825A65D089487BBF5FCB0D74D41CD7"><b>Mapped to Another Organization</b>: Another Experience Cloud organization has already mapped this report suite to their organization. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Retention Policy </p> </td> 
   <td colname="col2"> <p>The Analytics Data Privacy implementation requires that you have a data retention policy in place. </p> <p>This setting shows whether: </p> 
    <ul> 
     <li>A data retention policy is in place for this report suite, and </li> 
     <li>How long the data is retained by Adobe before it is deleted. The default data retention period is 25 months. </li> 
    </ul> <p>Note:  Adobe Analytics cannot assist you with processing requests to the Data Privacy API, i.e., processing access or deletion requests you receive from your end users, if the data retention period has not been set. Please contact your Customer Success Manager in order to set your data retention period. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Groups </p> </td> 
   <td colname="col2"> <p>Grouping functionality is not currently implemented. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Left-hand side bar </p> </td> 
   <td colname="col2"> <p>Click the funnel icon to open or close the side bar. </p> <p>The Organization Mapping section displays the number of report suites that fall into each of the described categories. </p> <p>The Data Retention Policy section displays each unique data retention policy currently in place for your organization and the number of report suites that were assigned that retention policy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Export to CSV </p> </td> 
   <td colname="col2"> <p>If you mark the checkbox next to one or more of the report suites, the <span class="uicontrol"> Export to CSV </span> option displays. This option lets you download a CSV file containing all current label definitions for all variables for all selected report suites. </p> <p>We recommend that your legal team review your labeling choices and this option facilitates this review. Instead of needing to perform the review while logged into the Data Governance UI, you can share the .CSV file with them. </p> <p><img placement="break"  src="assets/export_csv.png" width="300px" id="image_5FE821B2D07B402D8E0F6FE53D6FC52E" /> </p> </td> 
  </tr> 
 </tbody> 
</table>
