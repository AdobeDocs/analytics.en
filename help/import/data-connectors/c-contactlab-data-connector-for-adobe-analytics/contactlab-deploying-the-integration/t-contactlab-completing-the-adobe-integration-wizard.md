---
description: Steps to complete the integration wizard in the Data Connectors interface.
seo-description: Steps to complete the integration wizard in the Data Connectors interface.
seo-title: Completing the Adobe Integration Wizard
solution: Analytics
title: Completing the Adobe Integration Wizard
uuid: a8135be3-fba3-436d-8959-faed40b15088
index: y
internal: n
snippet: y
---

# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

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
   |  Link ID  | Select an eVar for collecting Link ID’s in real time.  |
   |  Message ID  | Select an eVar for collecting Message ID’s in real time.  |
   |  Recipient ID  | Select an eVar for collecting recipient ID’s in real time.  |
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
   1. Configure whether you will collect ID’s by manually updating your Analytics collection code or by using the automated solution. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
