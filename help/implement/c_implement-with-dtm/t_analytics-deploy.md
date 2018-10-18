---
description: Create an Adobe Analytics tool for deployment using Dynamic Tag Management. This procedure describes a manual (legacy) implementation.
keywords: Dynamic Tag Management
seo-description: Create an Adobe Analytics tool for deployment using Dynamic Tag Management. This procedure describes a manual (legacy) implementation.
seo-title: Manually implement Adobe Analytics (legacy)
solution: Marketing Cloud,Analytics,Target,Dynamic Tag Management
title: Manually implement Adobe Analytics (legacy)
uuid: 11cdf473-73a5-49d9-8728-2f965cc705ef
index: y
internal: n
snippet: y
---

# Manually implement Adobe Analytics (legacy)

Create an Adobe Analytics tool for deployment using Dynamic Tag Management. This procedure describes a manual (legacy) implementation.

For information about automatic implementation management, see [Add Adobe Analytics Tool](../c_implement-with-dtm/c_aa_tool/analytics_dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

If you want to change a manual configuration to automatic, edit a tool and click **[!UICONTROL Enable Automatic Configuration]**. 

1. Download [!DNL Analytics] measurement code:
   1. In [!DNL Adobe Experience Cloud], click **[!UICONTROL Reports & Analytics]** > **[!UICONTROL Admin Tools]**.
   1. Click **[!UICONTROL Code Manager]**.
   1. Click [JavaScript (new)](http://microsite.omniture.com/t2/help/en_US/sc/implement/?f=appmeasure_mjs) to download the code locally.
1. In Dynamic Tag Management, [create a web property](../c_implement-with-dtm/t_create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).

   ![](assets/dtm-property.png)

   After you create the web property, it is available for editing on the [!UICONTROL Web Properties] tab on the [!UICONTROL Dashboard]. Activating the web property is not required 

1. Add an [!DNL Adobe Analytics] tool to the property:
   1. On the [!UICONTROL Web Properties] tab, click the property.
   1. On the [!UICONTROL Overview] tab, click **[!UICONTROL Add a Tool]**.
   1. From the [!UICONTROL Tool Type] menu, select **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. Configure the following fields:

      |  Element  | Description  |
      |---|---|
      |  Tool Type  | The Experience Cloud solution, such as Analytics, Target, Social, and so on.  |
      |  Tool Name  |The name for this tool. This name displays on the [!UICONTROL Overview] tab under [!UICONTROL Installed Tools].  |
      |  Production Account ID  | A number for your production account for data collection. Dynamic Tag Management automatically installs the correct account in the production and staging environment.  |
      |  Staging Account ID  | A number used in your development or test environment. A staging account keeps your testing data separate from production.  |

1. Click **[!UICONTROL Create Tool]**.

   The installed tool displays on the [!UICONTROL Overview] tab.

   ![](assets/settings_gear.png)

1. To configure the code, click **[!UICONTROL Settings]** ( ![](assets/settings_gear.png)

   ).

   At a minimum, click **[!UICONTROL Cookies]** and configure your tracking server and SSL tracking server. 

1. Click **[!UICONTROL General]** and [insert the core AppMeasurement code](../c_implement-with-dtm/c_aa_tool/t_appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658).
1. Define a [page load rule](../c_implement-with-dtm/c_rules/t_rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) to collect [!DNL Analytics]data.

   You are now ready to define rules to collect analytics data. You might want to define a few data elements first. Data elements let you extract data from the page that you can use to configure your rule. To get started, you can define a page load rule that does not have any conditions to collect [!DNL Analytics] data on each page. 
1. [Add the header and footer code](../c_implement-with-dtm/c_headers_footers/t_header-footer-code.md#task_43C8DD699A514638B0620775C06423E5) on the Embed tab.

   For staging, you can leave the default Amazon hosting option. You can change it if needed before your production rollout. 
1. (Optional) Click **[!UICONTROL Settings]** ( ![](assets/settings_gear.png)) on the Options tab, and configure the [!UICONTROL Adobe Analytics] code.

   >[!NOTE]
   >
   >The settings on the [!UICONTROL Adobe Analytics] page (General, Cookies, and so on) override settings in your `s_code`. If these settings exist in your `s_code`, there is no need to reiterate them here.

