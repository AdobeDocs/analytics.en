---
description: After completing the integration wizard, you must deploy the integration code to your Adobe Analytics deployment code (s_code).
seo-description: After completing the integration wizard, you must deploy the integration code to your Adobe Analytics deployment code (s_code).
seo-title: Deploying the Integration Code
title: Deploying the Integration Code
uuid: b3fbda0b-4ed3-4967-84ee-6c66564606e7
index: y
internal: n
snippet: y
---

# Deploying the Integration Code{#deploying-the-integration-code}

After completing the integration wizard, you must deploy the integration code to your Adobe Analytics deployment code (s_code).

>[!NOTE]
>
>If you used Adobe TagManager or Dynamic Tag Management to deploy Adobe Analytics, you can easily add the integration code using one of those tools.

1. Go to the **[!UICONTROL Support]** tab and download and save the `integration code v2_0_1` resource from the Resources area of the integration. 

1. If applicable, make any necessary modifications to the code For more information, see [Modifying the Integration Code](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855). 
1. Include the Integrate Module if it is not already present in your Adobe Analytics deployment code. For more information, see [Including the Integrate Module](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e). 
1. Deploy the code using one of the following methods:

    * Use Adobe TagManager or Dynamic Tag Management to add the code. 
    * Or, deliver the code to the organizational resource that is responsible for updating your Adobe Analytics deployment code.

>[!IMPORTANT]
>
>Make sure you test deployment for this integration in a development/staging environment before deploying it to a production environment.

