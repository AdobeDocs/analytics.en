---
description: Use the Adobe Data Connectors Configuration Wizard to set up the integration.
title: Activate the Integration
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
exl-id: 18fb2f55-f1fb-4d97-bd1e-8c5e74dbde69
---
# Activate the Integration{#activate-the-integration}

Use the Adobe Data Connectors Configuration Wizard to set up the integration.

1. Start [Data Connectors](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Complete the Integration Wizard using the information in the following table:

| Field | Description |
|--- |--- |
|Report Suite|The report suite that receives the data from this integration.|
|Integration Name|Specify the integration name that Data Connectors displays in the report suite's Active Integration List.|
|E-Mail Address| Provide an email address to receive integration-related information.|
|Account ID|This is the unique identifier assigned to your organization by your Email Service Provider. It will be used when requesting email campaign data (e.g. # Sent, # Opened, # Clicked, etc.) from and sending visitor segments to your Email Service Provider.|
|Recipient ID|This ID is an encoded or numeric representation of an email address from the optivo® broadmail system. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the optivo® broadmail system and can be leveraged for remarketing purposes.|
|Message ID|(Required) Stores the unique mailing ID. These classification dimensions are created by the Data Connectors wizard for the Message ID: <br>a)**Campaigns**: Campaigns associated with the message. <br>b)**Channel**: The channel of transmission, this is constantly "optivo broadmail". <br>c)**Country Code**: This field contains the country code of the origin sender country. It is a constant "DE". <br>d) **Delivery Tool**: Method of transmission, always "Email".<br> e) **Message Name**: The name of the mailing, as it is configured in optivo® broadmail. <br>f) **Start Date**: Timestamp of the start of this mailing.|
|Post Click Time|(Required) This is needed to transmit information about a recipient action to optivo® broadmail after the recipient clicked a link in a mailing.|
|Post Click Product|(Required) This is needed to transmit information about a recipient action to optivo® broadmail after the recipient clicked a link in a mailing.|
|Post Click Action|(Required) This is needed to transmit information about a recipient action to optivo® broadmail after the recipient clicked a link in a mailing.|
|Hard Bounce|(Required) Specify the Adobe Analytics event that stores the hard bounces data imported from the email system. Number of email messages that were not delivered to recipients and are considered permanently undeliverable.|
|Soft Bounce|(Required) Specify the Adobe Analytics event that stores the soft bounces data imported from the email system. Number of email messages that were not delivered to recipients due to a delivery problem.|
|Clicked|(Required) Specify the Adobe Analytics event that stores the email clicked data importedfrom the email system. The Clicked event lets you see the number of visitors who clicked the email message.|
|Opened|(Required) Specify the Adobe Analytics event that stores the email opened data imported from the email system. The Opened event lets you see the number of visitors who opened the email message.|
|Sent|(Required) Specify the Adobe Analytics event that stores the email sent data imported from the email system. The Sent event lets you see the number of email messages that were sent.|
|Unsubscribed|(Required) Specify the Adobe Analytics event that stores the email unsubscribe data imported from the email system. The Unsubscribed event lets you see the number of visitors who opened the email message but then clicked the Unsubscribe link to opt-out of future email messages from your organization.|
|Segments|Enable existing segments to be used together with this integration (optional).|
|Access Requests|Enable the recommended access privileges.|
|Data Collection|Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. If you select this option, specify the unique identifiers used for this integration:<ul><li>Message ID Query String Parameter: This value represents the Message ID appended to the landing page URL by your email partner.</li><li>Recipient ID Query String Parameter: This value represents the Recipient ID appendedto the landing page URL by your email partner.</li></ul>|
|Dashboard and Bookmark Generation|Automatically generate a dashboard and bookmarks for the integration.|
