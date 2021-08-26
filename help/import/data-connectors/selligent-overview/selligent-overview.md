---
description: Use the Selligent data connector with Adobe Analytics.
title: Selligent Data Connector for Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
exl-id: baeabd9c-10bc-4733-8779-abfa81807c54
---
# Selligent Data Connector for Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>We will be end-of-lifing the Adobe Data Connector technology on August 1, 2021. [Learn more...](/help/import/data-connectors/data-connectors-eol.md)

This integration includes the following key benefits:

* Consolidate email marketing and analytics data into one reporting interface.
* Optimize email campaigns by conversion and contribution to revenue and site success.
* Re-market to key visitors and market segments based on dynamic marketing segments.

## Dynamic Marketing Segments {#section-a2216f3339304636bd5417249bd635a4}

This email integration supports dynamic marketing segments to help you drive your business. This integration features the following marketing segments, out of the box: 

|  Segment  | Description  |
|---|---|
| **Cart Abandonment Profile** | Help visitors convert to customers through fine-tuned campaigns specifically designed for those who are hesitant to complete carts.  |
| **Purchases Profile** | Increase repeat orders and average order value through campaigns targeted by visitor purchase patterns.  |
| **Product/Content View Behavioral Profile** | Reach prospective customers through marketing segments based on product views and content access profiling.  |
| **Custom Re-Marketing Segments** | Customers can also create and schedule custom re-marketing segments specific to the needs of their users.  |

## Before you Activate this Integration{#before-you-activate-this-integration}

Before activating this integration, review the following items against your deployments of Adobe Analytics and your email software.

Doing so will ensure the appropriate best practices and pre-requisites are in place prior to activation. This will result in an optimal and successful integration.

## Prerequisites for Adobe Analytics{#prerequisites-for-adobe-analytics}

Lists the necessary actions to take in Adobe Analytics before you can deploy the integration.

|  Prerequisite  | Notes  |
|---|---|
|  Select Report Suite  | Be advised that this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration.  |
|  Configure Analytics variables  | This integration requires custom events and custom eVars, and optionally additional events and additional eVars. See Configuring Analytics Variables for Selligent.  |
|  Authorized Representative  | Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.  |
|  Enable Adobe Data Warehouse™  | This integration requires the Data Warehouse to be enabled in order to generate remarketing segments. If you have not enabled the Adobe Data Warehouse, contact Adobe for details.  |
|  Recipient ID  | The integration requires that we capture and store a "Visitor ID" within a Analytics variable (eVar). The Visitor ID (often referred to as the "Recipient ID") is an encoded or numeric representation of an email address from the Selligent system. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled back into the Selligent system and can be leveraged for remarketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard.  |
|  External Tracking  | If you're not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the Selligent section below for details.  |
|  Privacy Compliance  | You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.  |

## Configure Analytics Variables for Selligent{#configure-analytics-variables-for-selligent}

This integration requires 2 eVars to be reserved for each report suite implementation.

Apart from these eVars, a few events may be reserved depending on the data from Selligent, which you would like to see in Analytics. These eVars and events are described as below: 

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Type </th> 
   <th colname="col2" class="entry"> Variable Name </th> 
   <th colname="col3" class="entry"> How it is Used </th> 
   <th colname="col4" class="entry"> Settings </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Message ID </td> 
   <td colname="col3"> To capture the individual email message campaign identification. </td> 
   <td colname="col4"> <p><b>Status</b>: Enabled </p> <p><b>Allocation</b>: Most Recent </p> <p><b>Expire After</b>: "Business Decision" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> To capture the anonymous identification for your customer who clicked the email campaign. </td> 
   <td colname="col4"> <p><b>Status</b>: Enabled </p> <p><b>Allocation</b>: Most Recent </p> <p><b>Expire After</b>: "Business Decision" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Sent </td> 
   <td colname="col3"> To store the number of emails sent from Selligent. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Delivered </td> 
   <td colname="col3"> To store the number of emails that were delivered. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Views </td> 
   <td colname="col3"> To store the number of unique emails that were viewed. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Clicks </td> 
   <td colname="col3"> To store the number of times any email was clicked. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Bounced </td> 
   <td colname="col3"> To store the number of emails that were bounced. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prerequisites for Selligent{#prerequisites-for-selligent}

Lists the necessary information to supply from your Selligent account before you can deploy the integration.

**Valid Selligent Account**

In order to use this Data Connectors integration, you must have a valid Selligent account.

**Account Information**

You will require the following information about your Selligent account during this integration setup:

* **Adobe Service URL**:

  The URL can be derived from the URL used to log on to the Selligent Marketing solution. Replace the "/simweb/login.aspx" part of the url with "/automation/omniture.asmx"

  E.g: `https://<client-specific install url>/automation/omniture.asmx` 

* **Query String Parameters:** These are appended in the landing page URL for Message ID and Recipient ID(Visitor ID). These are always MID and RID for Message ID and Recipient ID respectively.

* **Integration Token** Launch the Manager tool from inside Simweb and go to **[!UICONTROL Configuration]** > **[!UICONTROL System Settings]** > **[!UICONTROL General]** tab > **[!UICONTROL System]**. Under **[!UICONTROL Security]**, you can find the Integration token.

  ![](assets/selligent-integration_token.png)
