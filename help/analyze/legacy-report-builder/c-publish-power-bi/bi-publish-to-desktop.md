---
description: Explains how to pull Report Builder-published assets into Power BI Desktop
title: Pull published assets into Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Pull published assets into Power BI Desktop

{{legacy-arb}}

Explains how to pull Report Builder-published assets into Power BI Desktop

## Prerequisites {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* You need to have the latest Power BI Desktop version installed (April 2017 release) 
* This process assumes that you have already published Report Builder formatted tables or requests to the Power BI Service.

## Process {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

In the April 2017 update of Power BI Desktop, Microsoft released the ability to connect to datasets in the Power BI service. This feature allows you to create new reports off existing datasets you've already published to the cloud. You can leverage this feature to better collaborate and reduce duplicate efforts across your team.

1. In Power BI Desktop, go to **[!UICONTROL File]** > **[!UICONTROL Options and settings]** > **[!UICONTROL Options]** > **[!UICONTROL Preview features.]** 
1. Enable **[!UICONTROL Power BI Service Live Connection]** and click **[!UICONTROL OK]**. ![Click Power BI Service Live Connection and then click OK. ](assets/bi-preview-features.png)

1. Restart Power BI Desktop.
1. Once you have restarted the desktop, go to **[!UICONTROL Home]** > **[!UICONTROL Get Data]** > **[!UICONTROL More...]**.
1. Search for and select **[!UICONTROL Power BI service]**.
1. Under **[!UICONTROL Microsoft Power BI service]** > **[!UICONTROL My Workspace]**, select the dataset that you had previously published from Report Builder.

For more information, see [Microsoft blog post](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
