---
description: Explains how to pull Report Builder-published assets into Power BI Desktop
title: Pull published assets into Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
---
# Pull published assets into Power BI Desktop

Explains how to pull Report Builder-published assets into Power BI Desktop

## Prerequisites {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* You need to have the latest Power BI Desktop version installed (April 2017 release) 
* This process assumes that you have already published Report Builder formatted tables or requests to the Power BI Service.

## Process {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

In the April 2017 update of Power BI Desktop, Microsoft released the ability to connect to datasets in the Power BI service. This feature allows you to create new reports off existing datasets you've already published to the cloud. You can leverage this feature to better collaborate and reduce duplicate efforts across your team.

1. In Power BI Desktop, go to **[!UICONTROL File]** > **[!UICONTROL Options and settings]** > **[!UICONTROL Options]** > **[!UICONTROL Preview features.]** 
1. Enable **[!UICONTROL Power BI Service Live Connection]** and click **[!UICONTROL OK]**. ![](assets/bi-preview-features.png)

1. Restart Power BI Desktop.
1. Once you have restarted the desktop, go to **[!UICONTROL Home]** > **[!UICONTROL Get Data]** > **[!UICONTROL More...]**.
1. Search for and select **[!UICONTROL Power BI service]**.
1. Under **[!UICONTROL Microsoft Power BI service]** > **[!UICONTROL My Workspace]**, select the dataset that you had previously published from Report Builder.

For more information, see this [Microsoft blog post](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
