---
description: Use the Adobe Data Connectors Configuration Wizard to set up the integration.
title: Activate the Integration
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
exl-id: b0d6849b-975a-4476-a2d3-36abeee12273
---
# Activate the Integration{#activate-the-integration}

Use the Adobe Data Connectors Configuration Wizard to set up the integration.

1. Start [Data Connectors](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Complete the Integration Wizard using the information in the following table:

| Field | Description |
|--- |--- |
|Report Suite| The report suite that receives the data from this integration.|
|Integration Name|Specify the integration name that Data Connectors displays in the report suite's Active Integration List.|
|Integration UUID|Specify your DreamMail Integration UUID.|
|Client Name | Specify your DreamMail Client Name.|
|Site Name| Specify your DreamMail Site Name.|
|Bounce Backs| Number of email messages that were not delivered to recipients due to a delivery problem.|
|Delivered| Number of successful message deliveries.|
|Delivery Errors|Unsuccessful message deliveries.|
|HTML Opens| Number of visitors who opened the email message.|
|Invalids| Number of invalid email addresses.|
|Campaign|Marketing campaign ID.|
|Pass Alongs| The Clicked event lets you see the number of visitors who clicked the email message.|
|Email eVar|An email address from the DreamMail system. This "Email eVar" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the DreamMail system and can be leveraged for remarketing purposes.|
|Spotlight Event |Event that can be exported in re-marketing segments.|
|Spotlight Purchases |Event that can be exported in re-marketing segments.|
|Spotlight Value| Revenue event that can be exported in re-marketing segments.|
|TotalClicks| The Clicked event lets you see the number of visitors who clicked the email message.|
|Segments|This integration creates the partner-defined segments displayed in the Partner Segments section. Additionally, you can select existing Report Suite-Level segments to include in the integration.|
|Access Requests| Enable the recommended access privileges.|
|Data Collection|Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration (see ). Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. If you select this option, specify the unique identifiers used for this integration:<ul><li>Message ID Query String Parameter: This value represents the Message ID appended tothe landing page URL by your email partner.</li><li>Recipient ID Query String Parameter: This value represents the Recipient ID appendedto the landing page URL by your email partner.</li></ul>|
|Dashboard and Bookmark Generation|Automatically generate a dashboard and bookmarks for the integration.|
