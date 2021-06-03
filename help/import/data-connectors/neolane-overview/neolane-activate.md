---
description: Use the Adobe Data Connectors Configuration Wizard to set up the integration.
title: Activate the Integration
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
exl-id: d36c26ad-09c4-4a4d-a653-670c18f2ab19
---
# Activate the Integration{#activate-the-integration}

Use the Adobe Data Connectors Configuration Wizard to set up the integration.

1. Start [Data Connectors](https://experienceleague.adobe.com/docs/ analytics/import/dataconnectors/getting-started-data-connectors.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://experienceleague.adobe.com/docs/ analytics/import/dataconnectors/getting-started-data-connectors.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Complete the Integration Wizard using the information in the following table:

| Field | Description |
|--- |--- |
|Report Suite| The report suite that receives the data from this integration.|
|Integration Name|Specify the integration name that Data Connectors displays in the report suite's Active Integration List.|
|Clicked|Total number of email clicks.|
|Campaign ID |Stores the unique message ID. This is often stored in the campaign variable.|
|Opened |Total number of email opens.|
|Person Clicks| Number of persons who have clicked.|
|Processed |Total number of processed emails.|
|Broadlog ID|This ID is an encoded or numeric representation of an email address from the Neolane system. This "Broadlog ID" is associated with downstream visitor behavior on the site (cart Broadlog ID abandons, purchases, etc.) that is pulled into the Neolane system and can be leveraged for remarketing purposes.|
|Scheduled |Number of email messages that are scheduled for delivery.|
|Sent |Number of email messages that were sent.|
|Total Bounces| Number of email messages that were not delivered to recipients due to a delivery problem.|
|Unique Clicks| Number of distinct clicks.|
|Unique Opens| Number of distinct opens.|
|Unsubscribed|Number of visitors who opened the email message but then clicked the Unsubscribe link to opt-out of future email messages from your organization.|
|Segments|This integration creates the partner-defined segments displayed in the Partner Segments section. Additionally, you can select existing Report Suite-Level segments to include in the integration.|
|Access Requests| Enable the recommended access privileges.|
|Data Collection|Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. If you select this option, specify the unique identifiers used for this integration: <ul><li>Message ID Query String Parameter: This value represents the Message ID appended tothe landing page URL by your email partner.</li><li>Recipient ID Query String Parameter: This value represents the Recipient ID appendedto the landing page URL by your email partner.</li></ul>|
|Dashboard and Bookmark Generation|Automatically generate a dashboard and bookmarks for the integration.|
