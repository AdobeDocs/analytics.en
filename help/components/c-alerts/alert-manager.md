---
description: Manage alerts.
title: Alert Manager overview
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
---
# Alerts manager

The Alerts manager is structured very much like the [Segment Manager](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html) and the [Calculated Metric Manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html).

 ![](assets/alert-manager.png)

## Access the Alerts manager

1. In Adobe Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Alerts**].

## Available actions in the Alerts manager

In the Alerts manager, you can:

* Access the Alert Builder by clicking **[!UICONTROL + Add]**.
* Tag alerts. This allows you to organize them for ease of use.
* Delete alerts.
* Rename alerts.
* Approve alerts.
* Copy alerts.
* Enable/disable alerts.
* **Renew** an alert expiration date. When one or more alerts are selected, they can be renewed by clicking **[!UICONTROL Renew]**.This extends their expiration dates to be 1 year from the day **[!UICONTROL Renew]** was clicked, regardless of their original expiration date.
* Export an alert to a .CSV file.
* Edit alerts by double-clicking the alert title.
* Search for alerts.
* Add alerts to other report suites.
* Specify/change the owner of an alert.
* Add other filters.
* Define an alert **expiration date**.

## Configure columns

You can configure the information displayed for each alert in the Alerts manager by configuring the columns that are displayed.

To configure the visible columns in the Alerts manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Alerts]**. 

1. In the Alert manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Alerts manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Title and description | These values are provided in the Alert builder. To edit the title and description, select the title link to open the Alert builder.  |
   | Favorites  | Displays star icons next to each alert, allowing you to mark alerts as favorites. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Type | Shows whether the alert is an Analytics data alert or a Server call usage alert. |
   | Enabled | Shows whether the alert is currently enabled or disabled. | 
   | Report suite | Indicates in which report suite the alert was last saved.  |
   | Owner | Indicates who owns the alert. As a non-admin, you can see only alerts you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the alert, either by you or by people who shared the alert with you.  |
   | Expiration date | Shows the date and time when the alert is set to expire. |
   | Date modified | Indicates the date when the alert was last modified.  |

   {style="table-layout:auto"}
   
   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


