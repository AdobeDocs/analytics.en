---
description: The Data Connectors Integration Wizard steps you through the Data Connectors integration process.
seo-description: The Data Connectors Integration Wizard steps you through the Data Connectors integration process.
seo-title: Silverpop Integration
title: Silverpop Integration
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
---

# Silverpop Integration{#silverpop-integration}

The Data Connectors Integration Wizard steps you through the Data Connectors integration process.

To configure the integration: 

1. In the Adobe Experience Cloud, select Data Connectors™ from the products drop down list.
1. Click **[!UICONTROL Add New]** and select **[!UICONTROL By Name]** in the **[!UICONTROL Show]** drop down list.
1. Find the **Silverpop Engage 2.0** icon and drag it to an empty plug-in slot in your Analytics report suite to launch the Data Connectors Integration Wizard.
1. On the Silverpop Integration introduction page, review the text, then select the check box to accept the fees associated with the integration.
1. Select the Report Suite that you want to use for this integration.
1. Provide a friendly name to identify this integration, then click **[!UICONTROL Create and Configure this Integration]**.

   This page provides an overview of the integration, along with helpful links for more information. There are both Adobe and Silverpop fees associated with this integration. Contact your appropriate Sales Representatives for both organizations and make sure you understand the fee structure. 
1. On each page of the Data Connectors Integration Wizard, provide the required information, as described in the following table:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>Field</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>Configuration Section</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Description</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Integration Name </p> </td> 
   <td colname="col03"> <p>(1) Integration Settings </p> </td> 
   <td colname="col3"> <p>Specify the integration name that Data Connectors displays in the report suite's Active Integration List. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Download File </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p> For use with file download remarketing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>Used for remarketing to visitors without a known Silverpop ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Account ID </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>Specify your Silverpop Account ID (the unique identifier assigned to your organization by Silverpop), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Form Name </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>For use with form abandonment remarketing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Mailing ID </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>(Required) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>(Required) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Bounces </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>(Required)Specify the Analytics event that stores the email Total Bounces data imported from the email system. </p> <p>The Total-Bounces event lets you see the number of email messages that were not delivered to recipients due to a delivery problem. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Clicked </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>(Required)Specify the Analytics event that stores the email Clicked data imported from the email system. </p> <p>The Clicked event lets you see the number of visitors who clicked the email message. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> File Downloaded </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p> For use with file download remarketing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Form Completed </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>For use with form abandonment remarketing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Form Started </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>For use with form abandonment remarketing. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Opened </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>(Required) Specify the Analytics event that stores the email Opened data imported from the email system. </p> <p>The Opened event lets you see the number of visitors who opened the email message. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Sent </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>(Required) Specify the Analytics event that stores the email Sent data imported from the email system. </p> <p>The Sent event lets you see the number of email messages that were sent. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Unsubscribed </p> </td> 
   <td colname="col03"> <p>(2) Variable Mappings </p> </td> 
   <td colname="col3"> <p>(Required) Specify the Analytics event that stores the email Unsubscribe data imported from the email system. </p> <p>The Unsubscribed event lets you see the number of visitors who opened the email message but then clicked the Unsubscribe link to opt-out of future email messages from your organization. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Segments </p> </td> 
   <td colname="col03"> <p>(3) Data Settings </p> </td> 
   <td colname="col3"> <p>This integration creates the partner-defined segments displayed in the Partner Segments section. </p> <p>Additionally, you can select existing Report Suite-Level segments to include in the integration. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Access Requests </p> </td> 
   <td colname="col03"> <p>(3) Data Settings </p> </td> 
   <td colname="col3"> <p> (Required) Enable <span class="uicontrol"> Allow this integration to download product data</span>. </p> <p>Optional: Allow this integration to download revenue, orders, and units. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Data Collection </p> </td> 
   <td colname="col03"> <p>(3) Data Settings </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the s_code.js plug-in as the collection model for this integration (see <a href="../silverpop-overview/silverpop-analytics-code.md"> Analytics Plug-In Code</a>). </p> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p>If you select this option, specify the unique identifiers used for this integration: </p> <p> <b>Message ID Query String Parameter:</b>This value represents the Message ID appended to the landing page URL by your email partner. </p> <p> <b>Recipient ID Query String Parameter:</b> This value represents the Recipient ID appended to the landing page URL by your email partner. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Dashboard and Bookmark Generation </p> </td> 
   <td colname="col03"> <p>(4) Report Settings </p> </td> 
   <td colname="col3"> <p>Automatically generate a dashboard and bookmarks for the integration. </p> </td> 
  </tr> 
 </tbody> 
</table>

