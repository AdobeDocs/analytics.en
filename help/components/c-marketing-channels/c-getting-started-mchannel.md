---
title: Get Started with Marketing Channels
description: Learn about the Marketing Channels workflow, the automatic setup, and how to apply template report suite settings to multiple report suites.
feature: Marketing Channels
exl-id: 35938bf9-89ab-434f-9dc2-7a65251412ef
---
# Get started with Marketing Channels

>[!NOTE]
>
>To maximize effectiveness of Marketing Channels for Attribution IQ and Customer Journey Analytics, we have published some [revised best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Analytics administrators can manage marketing channels for their organizations as described in [Manage Marketing Channels](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Marketing Channels are commonly used to provide insight on how visitors arrive on your site. You can customize your Marketing Channel Processing Rules based on what channels you want to track, and how you want to track them.

Marketing Channels revolve around First and Last Touch metrics, which are components of standard conversion metrics.

## Marketing Channels workflow

![](assets/step1_icon.png) Define each channel based on your business requirements.

Defining the channels you use is one of the most important components of Marketing Channels. Defining the channels can require collaboration between several individuals in your organization. Here are a few questions to consider:

* Are you using a paid search? 
* Are you using email campaigns? Are you using multiple email campaigns that you would want to track separately? 
* Do you have affiliates that direct traffic to your site? Are there affiliates that you want to track individually? 
* Are there external campaigns that would be advantageous in tracking separately?
* Do you want to aggregate all social networking sites, or are there any that you want to track individually? 
* Are there other channels that might affect conversion that you want to track?

A list of recommended channels can be found in [Frequently Asked Questions and Examples](/help/components/c-marketing-channels/c-faq.md). Create a list of channels you want to use, so that enabling and defining them is easier when you create channels.

![](assets/step2_icon.png) Add marketing channels on the [!UICONTROL Marketing Channel Manager] page.

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

See [Channels and Rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md) for important prerequisite and conceptual information.

See [Add marketing channels](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md) for the procedure.

>[!NOTE]
>
>If Marketing Channels have not been previously configured, the [automatic setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md) displays. This setup provides several pre-configured channels that you can customize. Adobe recommends that you use these rules as a template. However, if you already have solid channel definitions, you can skip the automatic setup.

![](assets/step3_icon.png) Configure or refine each channels' rules on the [!UICONTROL Marketing Channel Processing Rules] page.

After you create channels on the [!UICONTROL Marketing Channel Manager] page, you configure the rules so that channels can retrieve and report data.

See [Marketing Channel Processing Rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

If channels were created in the automatic setup, the rules in those channels are defined. You can modify them to suit your needs.

## Automatic setup for Marketing Channels {#run-auto-setup}

The Marketing Channel report comes with a one-time setup page to get you started. It provides several marketing channels that you can use for tracking. You can skip this setup if you feel comfortable creating channels and rules. However, Adobe recommends that you allow the wizard to create the channels for you. The automatic setup lets you see how rules are constructed, or edit them for your own purposes. You can disable or delete the predefined channels at any time.

How to run the Marketing Channels automatic setup.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager], select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Step Result](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. (See [Marketing Channel Manager](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).) This page does not display if your report suite contains one or more marketing channels. You cannot access this page again unless you select another report suite that does not contain marketing channels.

1. Make sure the channels that you want to create are selected.

   When selected, **[!UICONTROL Email]**, **[!UICONTROL Display]**, and **[!UICONTROL Affiliate]** are required fields.

1. Click **[!UICONTROL Save]**.

## Apply template report suite settings to multiple report suites

How to use a master report suite as a template for testing your marketing channel configuration. To save time, you can apply this template to one or more production report suites in a mass update. You perform this task for channels and rule sets separately.

>[!NOTE]
>
>Apply channels from a template before you apply rule sets. Your channels must be the same across all report suites when performing this procedure.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the **[!UICONTROL Report Suite Manager]** page, select the template report suite, as well as one or more target report suites.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. On the **[!UICONTROL Select Master Report Suites]** page, select a template report suite.
1. Click **[!UICONTROL Save All]**.
1. Apply rules from a template to multiple report suites:
   1. Return to the [!UICONTROL Report Suite Manager] page.
   1. Select the template report suite, as well as one or more target report suites.
   1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Click **[!UICONTROL Save]**. If the Save button is disabled in this step, enable it by expanding one of the rules.
