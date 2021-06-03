---
description: This integration combines the power of email marketing software integrated feedback system and the behavioral reporting of Adobe Analytics to create powerful analytics and optimization opportunities for your organization.
title: optivo® broadmail Data Connector for Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
exl-id: fff63047-afa6-420d-9188-ec8ebe407a46
---
# optivo® broadmail Data Connector for Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>We will be end-of-lifing the Adobe Data Connector technology on August 1, 2021. [Learn more...](/help/import/data-connectors/data-connectors-eol.md)

This integration combines the power of email marketing software integrated feedback system and the behavioral reporting of Adobe Analytics to create powerful analytics and optimization opportunities for your organization.

[!DNL ~Partner~] is a professional email marketing software. Its main function is to create, send and evaluate newsletter and email campaigns. `[~Partner~]` is available as a cloud service (software as a service).

The `[~Partner~]` integration offers automated remarketing and data synchronization, leading to increased conversions and revenue. The integration enables marketers to synchronize automatically segments for their customers, based on their email interaction and site behavior. The automated data exchange of customizable segments helps you to create highly targeted email campaigns that boost sales, such as shopping cart abandonment and post purchase remarketing to cross-, up- and resell products.

This integration also exchanges metrics of successful email campaigns from `[~Partner~]` to Adobe Analytics. Crucial data are displayed centrally in your email campaign overview.

## Data Connectors Laboratory Program {#section-51f9864851b64d96873127b9ac9c9a2b}

This program is a fast track method for Adobe's third party platform partners to build integrations and deliver them to our joint market. The integrations are completely developed by our partners and made available on the Adobe Experience Cloud following community methodologies. They are made available without additional charge to Adobe customers of the Adobe Analytics and other Solutions and are provided on an as-is basis with no implied warranties from Adobe due to the third party nature of the integrations.

If you have questions regarding your current service, warrantee or licensing, please contact your Adobe Account Manager.

## Key Benefits and Features{#key-benefits-and-features}

This integration includes the following key benefits:

* Recover shoppers who browse and abandon 
* Increase sales with targeted cross-sell and up-sell remarketing 
* Automatic segment-based campaigns 
* Optimized campaigns in progress 
* Segments in [!DNL ~Partner~] for targeted remarketing 
* Constant campaign metric updates 
* Automated conversation triggers

## Dynamic Marketing Segments{#dynamic-marketing-segments}

This integration features the following dynamic marketing segments:

* **Purchase Profiles:** Increase repeat orders and average order value through campaigns targeted by visitor purchase patterns.
* **Product/Content View Behavioral Profile:** Reach prospective customers through marketing segments based on product views and content access profiling.
* **Cart Abandonment Profile:** Help visitors convert to customers through fine-tuned campaigns specifically designed for those who are hesitant to complete carts.
* **Effective Remarketing:** Customers can also create and schedule custom remarketing segments specific to the needs of their users.

## Before You Activate{#before-you-activate}

Before starting the Data Connectors integration for , complete the following requirements:

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Report Suite Specific:** Be advised this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration.
* **Available and configured Adobe Analytics variables:** This integration requires custom events and custom eVars.

* **Authorized Representative:** Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.
* **Message ID:** The integration requires that we capture and store a "Message ID" within a Adobe Analytics variable (eVar). These IDs are needed to identify the mailings you sent. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard.
*  **Partner:** The integration requires that we capture and store a [!UICONTROL ~Partner~] within a Adobe Analytics variable (eVar). This ID is an encoded or numeric representation of an email address from the [!UICONTROL ~Partner~] system. This [!UICONTROL ~Partner~] is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the [!UICONTROL ~Partner~] system and can be leveraged for remarketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard.
* **Post Click Time:** As a part of the setup process, this integration requires an assignment to an eVar that corresponds to the time of a post click action. This is needed to transmit information about a recipient action to [!UICONTROL ~Partner~] after the recipient clicked a link in a mailing.

* **Post Click Product:** As a part of the setup process, this integration requires an assignment to an eVar that corresponds to the offered product that is associated with a post click action. This is needed to transmit information about a recipient action to [!UICONTROL ~Partner~] after the recipient clicked a link in a mailing.

* **Post Click Type of Action:** As a part of the setup process, this integration requires an assignment to an eVar that corresponds to the type of a post click action. This is needed to transmit information about a recipient action to [!UICONTROL ~Partner~] after the recipient clicked a link in a mailing.

* **Privacy Compliance:** You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.

## Pricing{#pricing}

Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable.

 By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.

### Adobe Pricing Considerations {#section-1f4f46c0d969435db57d38c1c310a05a}

Current customers of the Adobe Analytics solution have no additional cost associated to using this Data Connectors Integration. Customers who have not yet move to the new Adobe Analytics product should contact their Adobe Account Representative for further details.

### Partner Pricing Considerations {#section-f8ca71df32224412a5101efb6e356529}

This integration is available to [!DNL ~Partner~] customers, however additional integration fees will apply. Please contact sales@optivo.com for pricing details. Please contact [!DNL ~Partner~] for pricing details.

## Adobe Analytics Variables{#adobe-analytics-variables}

This integration requires Adobe Analytics variables to track metrics.

After identifying the Event and eVars to use with this integration, they must be enabled in the Analytics Admin Console (see [Report Suites](https://experienceleague.adobe.com/docs/ analytics/admin/manage-report-suites/report-suites-admin.html) for instructions).
