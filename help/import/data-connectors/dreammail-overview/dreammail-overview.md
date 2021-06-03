---
description: This Adobe® Data Connectors™ email integration combines behavioral information from Analytics® with email marketing to create a powerful tool to redefine success measurement and target audiences with more relevant messaging.
title: DreamMail Data Connector for Adobe Analytics
uuid: f6c01bf8-4e6a-4163-9d41-f24fb5f06bdc
exl-id: a37bf616-0f2a-4009-825f-92c30e79336f
---
# DreamMail Data Connector for Adobe Analytics{#dreammail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>We will be end-of-lifing the Adobe Data Connector technology on August 1, 2021. [Learn more...](/help/import/data-connectors/data-connectors-eol.md)

This Adobe® Data Connectors™ email integration combines behavioral information from Analytics® with email marketing to create a powerful tool to redefine success measurement and target audiences with more relevant messaging.

Delivering relevant email messages to these market segments can result in entirely new revenue opportunities, driving increased conversion and revenue among new and existing email campaigns. For example, delivering relevant email messages based on products that were viewed during a visit or products that were left in an abandoned shopping cart has been proven to have dramatic impact on revenue, with minimal impact on cost because this is simply leveraging visitors your site is already getting.

This increase in marketing efficiency is one of the key benefits of integrating [!DNL Analytics] with [!DNL ~Partner~]. Additionally, this integration will automatically synchronize email metrics with [!DNL Analytics] data as frequently as hourly for closed-loop reporting.

## Key Benefits and Features{#key-benefits-and-features}

This integration includes the following key benefits:

* Consolidate email marketing and analytics data into one reporting interface.
* Optimize email campaigns by conversion and contribution to revenue and site success.
* Re-market to key visitors and market segments based on dynamic marketing segments.

## Dynamic Marketing Segments{#dynamic-marketing-segments}

This integration features the following dynamic marketing segments:

* **Purchase Profiles:** Increase repeat orders and average order value through campaigns targeted by visitor purchase patterns.
* **Product/Content View Behavioral Profile:** Reach prospective customers through marketing segments based on product views and content access profiling.
* **Cart Abandonment Profile:** Help visitors convert to customers through fine-tuned campaigns specifically designed for those who are hesitant to complete carts.
* Customers can also create and schedule custom remarketing segments specific to the needs of their users.

## Before You Activate{#before-you-activate}

Before starting the Data Connectors integration for , complete the following requirements:

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Report Suite Specific:** Be advised this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration.
* **Available and configured Analytics variables:** This integration requires custom events and custom eVars, and optionally additional events and additional eVars.

* **Authorized Representative:** Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.
* **Data Warehouse™:** This integration requires Data Warehouse to be enabled in order to generate remarketing segments. If you have not enabled Data Warehouse, contact Adobe for details.
* **[!DNL ~Partner~]:** The integration requires that we capture and store an email address within a Analytics variable (eVar). The " [!DNL ~Partner~]" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the [!DNL ~Partner~] system and can be leveraged for remarketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard.
* **External Tracking:** If you're not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the [!DNL ~Partner~] section below for details.
* **Privacy Compliance:** You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.

## Pricing{#pricing}

Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable.

 By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.

### Adobe Pricing Considerations {#section-1f4f46c0d969435db57d38c1c310a05a}

There might be recurring and implementation fees associated with this integration, including cost for an increased number of server calls incurred through this integration. Please contact your Adobe Account Representative for pricing details.

### ~Partner~ Pricing Considerations {#section-f8ca71df32224412a5101efb6e356529}

There might be recurring and implementation fees associated with this integration. Please contact [!DNL DreamMail] for pricing details.

## Analytics Integration Variables{#analytics-integration-variables}

This integration requires Analytics variables to track metrics.

After identifying the Event and eVars to use with this integration, they must be enabled in the Analytics Admin Console (see [Report Suites](https://experienceleague.adobe.com/docs/ analytics/admin/manage-report-suites/report-suites-admin.html) for instructions).
