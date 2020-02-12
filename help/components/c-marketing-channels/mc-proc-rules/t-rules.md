---
title: Create Marketing Channel processing rules
description: Create Marketing Channel processing rules, which determine if a visitor hit meets the criteria assigned to a channel.
---

# Create Marketing Channel processing rules

Create Marketing Channel processing rules, which determine if a visitor hit meets the criteria assigned to a channel.

This procedure uses an email rule as an example. The example assumes that you have added an email channel to your list of channels on the Marketing Channel Manager page.

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Select a report suite.

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).

1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Step Result](assets/marketing_channel_rules.png)

1. From the **[!UICONTROL Add New Rule Set]** menu, select **[!UICONTROL Email]**.

   Here you are not selecting your channel, but a template that populates the rule with a few of the necessary parameters.

   ![Step Result](assets/example_email.png)

   Use Boolean logic (if / then statements) to configure a rule. For example, in an email channel rule, provide the settings or information emphasized in the following rule statement:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   In this example, *`<value>`* is the query string parameter that you use for your email campaign, such as *`eml`*.
1. To continue creating rules, click **[!UICONTROL Add Rule]**.
1. To prioritize rules, drag-and-drop them to the desired position.
1. Click **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Frequently Asked Questions and Examples](/help/components/c-marketing-channels/mc-faq/c-faq.md)
