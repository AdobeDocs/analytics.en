---
description: null
title: Deploying the Integration
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
---

# Deploying the Integration{#deploying-the-integration}

Deploying this integration is a simple process that requires the following actions: 

## Complete the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Steps to complete the integration wizard in the Data Connectors interface.

1. Navigate to the Data Connectors (formerly Genesis) area within the Adobe Experience Cloud.
1. Launch the ContactLab integration wizard.
1. Choose the desired Report Suite and provide a name for the integration.
1. Configure the following items:

   |  Item  | Description  |
   |---|---|
   |  Email address  | The primary contact's email address  |
   |  Description  | (Optional) Description for this integration setup  |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   |  Item  | Description  |
   |---|---|
   |  Link ID  | Select an eVar for collecting Link ID's in real time.  |
   |  Message ID  | Select an eVar for collecting Message ID's in real time.  |
   |  Recipient ID  | Select an eVar for collecting recipient ID's in real time.  |
   |  Bounces  | Select a numeric event to receive daily bounces from ContactLab.  |
   |  Sent  | Select a numeric event to receive daily sends from ContactLab.  |
   |  Clicked  | Select a numeric event to receive daily total clicks from ContactLab.  |
   |  Opened  | Select a numeric event to receive daily total opens from ContactLab.  |
   |  Unsubscribed  | Select a numeric event to receive daily unsubscribes from ContactLab.  |

1. Enable data access and configure data collection.
   1. Rename classifications as needed.
   1. **[!UICONTROL Partner segments]** are standard remarketing segments that are included in your integration.
   1. Under **[!UICONTROL Your Segments]**, select any custom segments that you would like to include in this integration. You can create additional custom segments under the admin panel.
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to ContactLab in daily remarketing segments.
   1. Rename calculated metrics as needed.
   1. Configure whether you will collect ID's by manually updating your Analytics collection code or by using the automated solution. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID's.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

## Verify the Integration{#verifying-the-integration}

View your ContactLab integration setup within the Adobe Experience Cloud

1. View the integration activity log.
   1. In the Adobe Experience Cloud, navigate to **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**.

      ![](assets/integration_activity_log.png)
   
   1. Look for entries like **[!UICONTROL Classification Data imported successfully]**, **[!UICONTROL Metrics Data imported successfully]**, and **[!UICONTROL Metric Data exported successfully]**. These entries should appear within 1 day of successful deployment.
1. View your reporting data within Adobe Analytics.
   1. Navigate to **[!UICONTROL Custom Conversion]** > **[!UICONTROL Custom Conversion 1-10]** > **[!UICONTROL Message ID Reports]**.

      ![](assets/reporting.png)
   
   1. Look for ContactLab reporting. This data should appear within 24-48 hours of successful deployment.
