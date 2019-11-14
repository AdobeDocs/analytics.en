---
description: This Adobe® Data Connectors™ email integration combines behavioral information from Analytics® with emarsys email marketing to create a powerful tool to redefine success measurement and target audiences with more relevant messaging.
title: Emarsys Data Connector for Adobe Analytics
uuid: 6f2fbabc-dc6c-4975-887d-ec22eba42f9e
---

# Emarsys Data Connector for Adobe Analytics{#emarsys-data-connector-for-adobe-analytics}

This Adobe® Data Connectors™ email integration combines behavioral information from Analytics® with emarsys email marketing to create a powerful tool to redefine success measurement and target audiences with more relevant messaging.

 Delivering relevant email messages to these market segments can result in entirely new revenue opportunities, driving increased conversion and revenue among new and existing email campaigns. For example, delivering relevant email messages based on products that were viewed during a visit or products that were left in an abandoned shopping cart has been proven to have dramatic impact on revenue, with minimal impact on cost because this is simply leveraging visitors your site is already getting.

This increase in marketing efficiency is one of the key benefits of integrating [!DNL Analytics] with emarsys. Additionally, this integration will automatically synchronize email metrics with [!DNL Analytics] data as frequently as hourly for closed-loop reporting.

## Key Benefits{#key-benefits}

Key benefits of this integration.

* Consolidate email marketing and analytics data into one reporting interface 
* Optimize email campaigns by conversion and contribution to revenue and site success 
* Re-market to key visitors and market segments based on dynamic marketing segments

## Dynamic Marketing Segments{#dynamic-marketing-segments}

This Data Connectors email integration supports dynamic marketing segments to help you drive your business.

This integration features the following marketing segments, out of the box:

* **Purchase Profiles:** Increase repeat orders and average order value through campaigns targeted by visitor purchase patterns.
* **Product/Content View Behavioral Profile:** Reach prospective customers through marketing segments based on product views and content access profiling.
* **Cart Abandonment Profile:** Help visitors convert to customers through fine-tuned campaigns specifically designed for those who are hesitant to complete carts.
* Customers can also create and schedule custom remarketing segments specific to the needs of their users.

## Integration Procedure and Prerequisites{#integration-procedure-and-prerequisites}

Using a "plug and play" wizard, intuitive step-by-step processes will walk you through points of system synchronization and initialize the integration.

This Data Connectors integration requires the following:

### Adobe Prerequisites {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Data Warehouse 
* Adobe [!DNL Analytics] account 
* Available and configured [!DNL Analytics] variables, including eVars and custom events.

### Partner Prerequisites: {#section-bcb904574ccf42308bcf7a15e45b4d58}

* An active emarsys account

For step-by-step integration instructions, see [Running the Data Connectors Integration Wizard.](/help/import/data-connectors/emarsys-overview/emarsys-wizard.md)

## Pricing{#pricing}

This Data Connectors integration includes pricing considerations that you need to be aware of.

### Adobe Pricing Considerations {#section-2d1c79c895a5479bad8fdd97961ba6a3}

There might be recurring and implementation fees associated with this integration. Please contact your Adobe Account Representative for pricing details.

### Partner Pricing Considerations {#section-c6afad08c34b43e3a7a3637eea3328c3}

There might be fees associated with this integration. Contact your relationship manager for pricing information.

## What You Should Know Before Activating This Integration{#what-you-should-know-before-activating-this-integration}

Before activating this integration, review the following items against your deployments of Adobe Analytics and your email software.

Doing so will ensure the appropriate best practices or pre-requisites are in place prior to activation, which will result in an optimal and successful integration. Review the following information about this Data Connectors integration as it relates to emarsys:

* **Valid emarsys Account:** In order to use the Data Connectors email integration, a client must have a valid emarsys account.
* **Current Customer of emarsys:** This integration requires you to be a customer of both Adobe and emarsys. If you are not currently a customer of emarsys, you will not have the information necessary to complete the integration wizard. If you are currently a customer of emarsys, you will need your emarsys Account ID, or the unique identifier assigned to your organization, in order to complete the integration wizard.
* After completing the Data Connectors wizard, contact your emarsys Account Manager to activate the integration in your emarsys eMarketing Suite.

### Adobe Analytics{#adobe-analytics}

Review the following information about this Data Connectors integration as it relates to Adobe Analytics:

* **Report Suite Specific:** Be advised this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration.
* **Authorized Representative:** Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.
* **Data Warehouse:** This integration requires the Data Warehouse to be enabled in order to generate remarketing segments. If you have not enabled the Data Warehouse, contact Adobe for details.
* **Recipient ID:** The integration requires that we capture and store a "Visitor ID" within a Analytics variable (eVar). The Visitor ID (often referred to as the "Recipient ID") is an encoded or numeric representation of an email address from the emarsys system. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the emarsys system and can be leveraged for remarketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard.
* **External Tracking:** If you're not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the emarsys section below for details.
* **Privacy Compliance:** You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.

