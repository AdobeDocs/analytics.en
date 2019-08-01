---
description: Lists the necessary actions to take in Adobe Analytics before you can deploy the integration.
seo-description: Lists the necessary actions to take in Adobe Analytics before you can deploy the integration.
seo-title: Prerequisites for Adobe Analytics
solution: Analytics
title: Prerequisites for Adobe Analytics
uuid: d799420d-7b06-4086-a6c6-18971296876c
index: y
internal: n
snippet: y
---

# Prerequisites for Adobe Analytics{#prerequisites-for-adobe-analytics}

Lists the necessary actions to take in Adobe Analytics before you can deploy the integration.

|  Prerequisite  | Notes  |
|---|---|
|  Select Report Suite  | Be advised that this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration.  |
|  Configure Analytics variables  | This integration requires custom events and custom eVars, and optionally additional events and additional eVars. See Configuring Analytics Variables for Selligent.  |
|  Authorized Representative  | Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.  |
|  Enable Adobe Data Warehouse™  | This integration requires the Data Warehouse to be enabled in order to generate remarketing segments. If you have not enabled the Adobe Data Warehouse, contact Adobe for details.  |
|  Recipient ID  | The integration requires that we capture and store a "Visitor ID" within a Analytics variable (eVar). The Visitor ID (often referred to as the "Recipient ID") is an encoded or numeric representation of an email address from the Selligent system. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled back into the Selligent system and can be leveraged for remarketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard.  |
|  External Tracking  | If you’re not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the Selligent section below for details.  |
|  Privacy Compliance  | You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.  |

