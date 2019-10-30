---
description: null
seo-description: null
seo-title: Deploying the Integration
solution: Analytics
title: Deploying the Integration
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
---

# Deploying the Integration{#deploying-the-integration}

Deploying this integration is a simple process that consists of completing the Adobe Integration Wizard and verifying the integration.

## Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Steps to complete the integration wizard in the Data Connectors interface.

1. Navigate to the Data Connectors (formerly Genesis) area within the Adobe Experience Cloud.
1. Launch the Dynamic Signal integration wizard.
1. Choose the desired Report Suite and provide a name for the integration.
1. Configure the following items:

   |  Item  | Description  |
   |---|---|
   |  Email address  | The primary contact's email address.  |
   |  Description  | (Optional) Description for this integration setup.  |
   |  Community ID  | You can obtain this ID from your Dynamic Signal representative.  |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   |  Item  | Description  |
   |---|---|
   |  Tracking Code  | Select an available eVar variable from your report suite.  |

1. Review the classifications that will be created for this integration.
1. Check the box to create the Dynamic Signal integration dashboard (optional, but highly recommended).
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
1. **Important**: Once you have completed the wizard, you must notify your Dynamic Signal representative so that they can activate the integration on the VoiceStorm platform.

## Verifying the Integration{#verifying-the-integration}

Steps to view your Dynamic Signal VoiceStorm integration setup within the Adobe Experience Cloud

1. View your Dynamic Signal integration setup in the integration activity log.
   1. In the Adobe Experience Cloud, navigate to  **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]** .

      ![](assets/integration_activity_log.png)   
   
   1. Look for entries like **[!UICONTROL Classification Data imported successfully]**. These entries should appear within 24 hours of successful deployment.
1. Review your Dynamic Signal reports within Adobe Analytics using the Dashboard that was automatically created for you using the Adobe Integratipn wizard (Step 7). Alternatively, you can navigate to the Dynamic Signal reporting within the Adobe Analytics menu structure - refer to the following screen shots.

   **Note**: This data should appear within 24-48 hours of successful deployment.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
