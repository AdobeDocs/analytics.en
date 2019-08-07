---
description: After completing the integration wizard, you must deploy the integration configuration object to your web property.
seo-description: After completing the integration wizard, you must deploy the integration configuration object to your web property.
seo-title: Deploy the Integration Configuration Object
solution: Analytics
title: Deploy the Integration Configuration Object
uuid: e951c864-2914-4324-9f03-5069d4f75d99
index: y
internal: n
snippet: y
---

# Deploy the Integration Configuration Object{#deploy-the-integration-configuration-object}

After completing the integration wizard, you must deploy the integration configuration object to your web property.

In many cases, the easiest way to deploy the integration configuration object is to include it with your Adobe Analytics deployment code.

>[!NOTE]
>
>If you use Adobe TagManager or Dynamic Tag Management to deploy Adobe Analytics, you can easily add the integration configuration object through that tool.

1. Navigate to the **[!UICONTROL Resources]** > **[!UICONTROL Support]** tab of the integration.
1. Download and save the **[!UICONTROL Kampyle Integration Code (JS)]** resource. The code looks similar to this:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Deploy the code using one of the following methods:

       | **You use Adobe TagManager or Dynamic Tag Management.** | Use the tag management interface to add the code. |
       |---|---|
       | **In all other cases** | Deliver the code to the organizational resource that is responsible for updating your Adobe Analytics deployment code.  |

