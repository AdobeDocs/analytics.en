---
description: null
seo-description: null
seo-title: Deploying the Integration
solution: Analytics
title: Deploying the Integration
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
---

# Deploying the Integration{#deploying-the-integration}

Deploying this integration is a simple process that requires the following actions: 

## Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Steps to complete the integration wizard in the Data Connectors interface.

1. Navigate to the Data Connectors (formerly Genesis) area within the Adobe Experience Cloud.
1. Launch the Responsys integration wizard.
1. Choose the desired Report Suite and provide a name for the integration.
1. Configure the following items:

   |  Item  | Description  |
   |---|---|
   |  Email address  | The primary contact's email address  |
   |  Description  | (Optional) Description for this integration setup  |
   |  Account ID  | Obtained by contacting Responsys Support Team at support@responsys.com  |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   |  Item  | Description  |
   |---|---|
   |  Message ID  | Select an eVar for collecting Message ID's in real time.  |
   |  Recipient ID  | Select an eVar for collecting recipient ID's in real time.  |
   |  Total Bounces  | Select a numeric event to receive daily bounces from Responsys.  |
   |  Email Sent  | Select a numeric event to receive daily sends from Responsys.  |
   |  Clicked  | Select a numeric event to receive daily total clicks from Responsys.  |
   |  Opened  | Select a numeric event to receive daily total opens from Responsys.  |
   |  Unsubscribed  | Select a numeric event to receive daily unsubscribes from Responsys.  |
   |  Delivered  | Select a numeric event to receive daily delivers from Responsys.  |

1. Enable data access and configure data collection.
   1. Rename classifications as needed.
   1. **[!UICONTROL Partner segments]** are standard remarketing segments that are included in your integration.
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to Responsys in daily remarketing segments.
   1. Configure whether you will collect ID's by manually updating your Analytics collection code or by using the automated solution. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID's.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

## Configuring within the Responsys System{#configuring-within-the-responsys-system}

Activating the integration involves contacting Responsys Support.

After completing the integration wizard, you must activate the integration within Responsys.

To do so, please contact Responsys support team at support@responsys.com.
