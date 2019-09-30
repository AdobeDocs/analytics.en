---
description: Describes the marketing efficiencies achieved through the integration.
seo-description: Describes the marketing efficiencies achieved through the integration.
seo-title: Lyris Data Connector for Adobe Analytics
solution: Analytics
title: Lyris Data Connector for Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
---

# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

Describes the marketing efficiencies achieved through the integration.

The Adobe® Data Connectors™ email integration combines behavioral information from Adobe Analytics with Lyris email marketing to redefine success measurement and target audiences with more relevant messaging.

Delivering relevant email messages to these market segments can result in entirely new revenue opportunities, driving increased conversion and revenue among new and existing email campaigns. For example, delivering relevant email messages based on products that were viewed during a visit or products that were left in an abandoned shopping cart has been proven to have dramatic impact on revenue, with minimal impact on cost because this is simply leveraging visitors your site is already getting.

This increase in marketing efficiency is one of the key benefits of integrating Adobe Analytics with Lyris. Additionally, this integration will automatically synchronize email metrics with Adobe Analytics data as frequently as hourly for closed-loop reporting.

## Key Benefits and Features{#key-benefits-and-features}

Describes the main benefits of integrating Lyris and Adobe Marketing Reports and Analytics.

The integration of Lyris and Adobe Analytics provides the following key benefits:

* Consolidate email marketing and analytics data into one reporting interface 
* Optimize email campaigns by conversion and contribution to revenue and site success 
* Re-market to key visitors and market segments based on dynamic marketing segments

### Dynamic Marketing Segments

The email integration supports dynamic marketing segments to help you drive your business. This integration features the following marketing segments, out of the box:

* **Cart Abandonment Profile**: Help visitors convert to customers through fine-tuned campaigns specifically designed for those who are hesitant to complete carts 
* **Purchase Profiles**: Increase repeat orders and average order value through campaigns targeted by visitor purchase patterns 
* **Product/Content View Behavioral Profile**: Reach prospective customers through marketing segments based on product views and content access profiling 
* Customers can also create and schedule **custom re-marketing segments** specific to the needs of their users.

## Integration Prerequisites{#integration-prerequisites}

Describes the prerequisites for a successful integration.

Before you activate this integration, review the following items against your deployments of Adobe Analytics and your email software.

This ensures that the appropriate best practices and pre-requisites are in place prior to activation, which will result in an optimal and successful integration.

### Prerequisites for Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Report-Suite specific**: Be advised that this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration 
* **Available and configured Analytics variables**: This integration requires custom events and custom eVars, and optionally additional events and additional eVars.

* **Authorized Representative**: Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above. 
* **Adobe Analytics data warehouse**: This integration requires Adobe Analytics data warehouse to be enabled in order to generate re-marketing segments. If you have not enabled data warehouse, contact Adobe for details. 
* **Recipient ID**: The integration requires that we capture and store a "Visitor ID" within an Analytics variable (eVar). The Visitor ID (often referred to as the "Recipient ID") is an encoded or numeric representation of an email address from the Lyris system. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled back into the Lyris system and can be leveraged for re-marketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard. 
* **External Tracking**: If you are not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the Lyris section below for details 
* **Privacy Compliance**: You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications, requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.

### Prerequisites for Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Valid Lyris Account**: In order to use this Data Connector integration, you must have a valid Lyris account. 
* **Account Information**: You will require the following information about your Lyris account during this integration setup:

    * *Lyris API Key*: Used for data population 
    * *Query String Parameters*: These are appended in the landing page URL for Message ID and Recipient ID (Visitor ID). 
    * *Lyris Server/URL*: The server value that you use in the Lyris system 
    * *Lyris Site ID*: Also known as “Customer ID”, this is the unique value for your instance of Lyris HQ. This can be located under “Customer Info” in the “Account Home” section of EmailLabs.

## Configure Adobe Analytics variables for Lyris{#configure-adobe-analytics-variables-for-lyris}

Describes the eVars and Events to be reserved for each report suite implementation.

This integration requires at least 2 eVars to be reserved for each report suite implementation. Apart from these eVars, a few events may be reserved depending on which Lyris data you would like to see in Analytics. These eVars and events are described in the table below: 

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Type </th> 
   <th colname="col2" class="entry"> Variable Name </th> 
   <th colname="col3" class="entry"> How the Variable is used </th> 
   <th colname="col4" class="entry"> Settings </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Message ID </td> 
   <td colname="col3"> To capture the individual email message campaign identification </td> 
   <td colname="col4"> <p>Status: Enabled </p> <p>Allocation: Most Recent </p> <p>Expire After: “Business Decision” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> To capture the anonymous identification for your customer who clicked the email campaign </td> 
   <td colname="col4"> <p>Status: Enabled </p> <p>Allocation: Most Recent </p> <p>Expire After: “Business Decision” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Emails Sent </td> 
   <td colname="col3"> To store no. of emails sent from Lyris </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Emails Opened </td> 
   <td colname="col3"> To store no. of emails that were opened </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Unique Emails Opened </td> 
   <td colname="col3"> To store no. of unique emails that were opened </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Email Click-throughs </td> 
   <td colname="col3"> To store no. of times any email was clicked </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Email Bounces </td> 
   <td colname="col3"> To store the no. of emails that were bounced </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Email Unsubscribes </td> 
   <td colname="col3"> To store the no. of email subscriptions that were disabled </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
 </tbody> 
</table>
