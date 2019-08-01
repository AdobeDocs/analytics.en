---
description: The Data Connectors Integration Wizard steps you through the Data Connectors integration process.
seo-description: The Data Connectors Integration Wizard steps you through the Data Connectors integration process.
seo-title: Running the Data Connectors Integration Wizard
title: Running the Data Connectors Integration Wizard
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
index: y
internal: n
snippet: y
---

# Running the Data Connectors Integration Wizard{#running-the-data-connectors-integration-wizard}

The Data Connectors Integration Wizard steps you through the Data Connectors integration process.

To configure the integration: 

1. Log in to the Marketing Cloud.
1. On the Analytics home page, click the Data Connectors™ icon on the pinwheel or tool bar.
1. On the Data Connectors page, select the Report Suite where you want to configure the integration.

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Delivra** icon.
1. Drag the **Delivra** icon to an empty plug-in slot in your Analytics report suite to launch the Data Connectors Integration Wizard.
1. On the Delivra Integration introduction page, review the text, then select the check box to accept the fees associated with the integration, then click **Next**.

   This page provides an overview of the integration, along with helpful links for more information. There are both Adobe and Delivra fees associated with this integration. Contact your appropriate Sales Representatives for both organizations and make sure you understand the fee structure. 
1. On each page of the Data Connectors Integration Wizard, provide the required information, as described in the following table:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>WIZARD PAGE #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FIELD</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Integration Name </p> </td> 
   <td colname="col3"> <p>Specify the integration name that Data Connectors displays in the report suite’s Active Integration List. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Integration Email Address </p> </td> 
   <td colname="col3"> <p>Specify the email address that receives all notifications related to this integration, then click <b>Next</b> to proceed to Step 2 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Account ID </p> </td> 
   <td colname="col3"> <p>Specify your Delivra Account ID (the unique identifier assigned to your organization by Delivra), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Message ID </p> </td> 
   <td colname="col3"> <p>Identify the Analytics eVar used for tracking the email Message ID. </p> <p>The Message ID is used for marketing/remarketing campaigns. The Message ID is often referred to as the "Tracking Code." </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identify the Analytics eVar used for tracking the email Recipient ID. </p> <p>The Recipient ID is used for marketing/remarketing campaigns. The Message ID is often referred to as the "Visitor Code." </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Acceptance Check Box </p> </td> 
   <td colname="col3"> <p>Review the information displayed next to the Acceptance check box: </p> <p><i>I understand that by enabling "Recipient ID" tracking, this feature may track personally identifiable information of our site visitors. This has privacy implications requiring the implementation of appropriate procedures by my organization, such as providing notice to, and consent of, our site visitors. </i> </p> <p>If you agree to the acceptance statement, select the check box, then click <b>Next</b> to proceed to Step 4 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Client-Defined Report Suite-Level Segments </p> </td> 
   <td colname="col3"> <p>This integration creates the partner-defined segments displayed on the left side of the Integration Segments page of the Integration Wizard. </p> <p>Additionally, you can select existing Report Suite-Level segments to include in the integration. </p> <p>Select the desired segments on the right side of the page, then click <b>Next</b> to proceed to Step 5 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicked </p> </td> 
   <td colname="col3"> <p>Specify the Analytics event that stores the email Clicked data imported from the email system. </p> <p>The Clicked event lets you see the number of visitors who clicked the email message. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Opened </p> </td> 
   <td colname="col3"> <p>Specify the Analytics event that stores the email Opened data imported from the email system. </p> <p>The Opened event lets you see the number of visitors who opened the email message. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Sent </p> </td> 
   <td colname="col3"> <p>Specify the Analytics event that stores the email Sent data imported from the email system. </p> <p>The Clicked event lets you see the number of email messages that were sent. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Total Bounces </p> </td> 
   <td colname="col3"> <p>Specify the Analytics event that stores the email Total Bounces data imported from the email system. </p> <p>The Total-Bounces event lets you see the number of email messages that were not delivered to recipients due to a delivery problem. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Unsubscribed </p> </td> 
   <td colname="col3"> <p>Specify the Analytics event that stores the email Unsubscribe data imported from the email system. </p> <p>The Unsubscribed event lets you see the number of visitors who opened the email message but then clicked the Unsubscribe link to opt-out of future email messages from your organization. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> Shares </td> 
   <td colname="col3"> <p>Specify the number of times the email message was shared to a social network, then click <b>Next</b> to proceed to Step 6 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Data Collection: JavaScript Plug-in </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the plug-in as the collection model for this integration, then click <b>Next</b> to proceed to Step 7 of the Wizard. </p> <p> <p>Note:  The Automated Solution is the default selection. </p> </p> <p>Contact your Adobe Consultant to get a copy of the JavaScript Plug-in used for this integration. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Data Collection: Automated Solution </p> </td> 
   <td colname="col3"> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p> <p>Note:  The Automated Solution is the default selection. </p> </p> <p>If you select this option, specify the unique identifiers used for this integration: </p> <p><b>Message ID Query String Parameter:</b>This value represents the Message ID appended to the landing page URL by your email partner. </p> <p><b>Recipient ID Query String Parameter:</b> This value represents the Recipient ID appended to the landing page URL by your email partner. </p> <p>Click <b>Next</b> to proceed to Step 7 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Integration Summary </p> </td> 
   <td colname="col3"> <p>Verify the integration parameters by clicking the plus sign (+) next to each category, then click <b>Save</b> to proceed to Step 8 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integration Complete </p> </td> 
   <td colname="col3"> <p>Click <b>Finish</b> to complete the integration. </p> <p><b>IMPORTANT:</b> Analytics does not save the integration settings until you click <b>Finish</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

