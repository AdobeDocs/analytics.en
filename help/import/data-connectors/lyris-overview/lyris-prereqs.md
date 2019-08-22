---
description: Describes the prerequisites for a successful integration.
seo-description: Describes the prerequisites for a successful integration.
seo-title: Integration Prerequisites
solution: Analytics
title: Integration Prerequisites
uuid: ac93bf4d-a071-4fac-9d42-c4856463cbb6
index: y
internal: n
snippet: y
---

# Integration Prerequisites{#integration-prerequisites}

Describes the prerequisites for a successful integration.

Before you activate this integration, review the following items against your deployments of Adobe Analytics and your email software.

This ensures that the appropriate best practices and pre-requisites are in place prior to activation, which will result in an optimal and successful integration.

## Prerequisites for Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Report-Suite specific**: Be advised that this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration 
* **Available and configured Analytics variables**: This integration requires custom events and custom eVars, and optionally additional events and additional eVars.

  See [Configure Analytics variables for Lyris](../lyris-overview/lyris-analytics-variables.md#task-e70a62dc096d4f548d5070a67822f5e7)

* **Authorized Representative**: Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above. 
* **Adobe Analytics data warehouse**: This integration requires Adobe Analytics data warehouse to be enabled in order to generate re-marketing segments. If you have not enabled data warehouse, contact Adobe for details. 
* **Recipient ID**: The integration requires that we capture and store a "Visitor ID" within an Analytics variable (eVar). The Visitor ID (often referred to as the "Recipient ID") is an encoded or numeric representation of an email address from the Lyris system. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled back into the Lyris system and can be leveraged for re-marketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard. 
* **External Tracking**: If you are not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the Lyris section below for details 
* **Privacy Compliance**: You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications, requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.

## Prerequisites for Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Valid Lyris Account**: In order to use this Data Connector integration, you must have a valid Lyris account. 
* **Account Information**: You will require the following information about your Lyris account during this integration setup:

    * *Lyris API Key*: Used for data population 
    * *Query String Parameters*: These are appended in the landing page URL for Message ID and Recipient ID (Visitor ID). 
    * *Lyris Server/URL*: The server value that you use in the Lyris system 
    * *Lyris Site ID*: Also known as “Customer ID”, this is the unique value for your instance of Lyris HQ. This can be located under “Customer Info” in the “Account Home” section of EmailLabs.

