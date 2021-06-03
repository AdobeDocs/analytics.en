---
description: Use the Adobe Data Connectors Configuration Wizard to set up the integration.
title: Activate the Integration
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
exl-id: 520a2b59-5595-4337-b71c-ea0448bf9267
---
# Activate the Integration {#activate-the-integration}

Use the Adobe Data Connectors Configuration Wizard to set up the integration.

1. Start [Data Connectors](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Complete the Integration Wizard using the information in the following table:

| Field | Description |
|--- |--- |
|Report Suite|The report suite that receives the data from this integration.|
|Integration Name|Specify the integration name that Data Connectors displays in the report suite's Active Integration List.|
|Account ID|Specify your Aprimo Account ID.|
|Recipient ID|This ID is an encoded or numeric representation of an email address from the Aprimo system. This "Recipient ID" is associated with downstream visitor behavior on the site Recipient ID (cart abandons, purchases, etc.) that is pulled into the Aprimo system and can be leveraged for remarketing purposes.|
|Clicked|(Required) Specify the Adobe Analytics event that stores the email Clicked data imported from the email system. The Clicked event lets you see the number of visitors who clicked the email message.|
|Message ID|(Required) Stores the unique mailing ID.|
|Opened|(Required) Specify the Adobe Analytics event that stores the email Opened data imported from the email system. The Opened event lets you see the number of visitors who opened the email message.|
|Recipient ID|(Required) Stores the unique visitor ID.|
|Sent|(Required) Specify the Adobe Analytics event that stores the email Sent data imported from the email system. The Sent event lets you see the number of email messages that were sent.|
|Bounces|(Required) Specify the Adobe Analytics event that stores the email Total Bounces data imported from the email system. The Total-Bounces event lets you see the number of email messages that were not delivered to recipients due to a delivery problem.|
|Unsubscribed|(Required) Specify the Adobe Analytics event that stores the email Unsubscribe data imported from the email system. The Unsubscribed event lets you see the number of visitors who opened the email message but then clicked the Unsubscribe link to opt-out of future email messages from your organization.|
|Segments|This integration creates the partner-defined segments displayed in the Partner Segments section. Additionally, you can select existing Report Suite-Level segments to include in the integration.|
|Access Requests|Enable the recommended access privileges.|
|Data Collection|Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration.|
Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. If you select this option, specify the unique identifiers used for this integration:
<ul><li>Message ID Query String Parameter: This value represents the Message ID appended tothe landing page URL by your email partner.</li>
<li>Recipient ID Query String Parameter: This value represents the Recipient ID appendedto the landing page URL by your email partner.</li></ul>|
|Dashboard and Bookmark Generation|Automatically generate a dashboard and bookmarks for the integration.|
