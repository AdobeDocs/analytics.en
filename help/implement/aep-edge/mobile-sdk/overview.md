---
title: Implement Adobe Analytics using the Adobe Experience Platform Mobile SDK
description: Use the Mobile SDK extension in Adobe Experience Platform Data Collection to send data to Adobe Analytics.
---

# Implement Adobe Analytics using the Adobe Experience Platform Mobile SDK

The Adobe Experience Platform Mobile SDK helps power Adobe's Experience Cloud solutions and services in your mobile apps. It is available for Android, iOS, and various cross-platform development frameworks. Configuration is handled through the Adobe Experience Platform Data Collection UI.

To send data to Adobe Experience Edge using the Mobile SDK:

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection).
2. Select the desired property from the list, or [set up a mobile property](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Go to the Extensions tab, and install the [Identity for Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) extension.
4. Install the [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Configure a datastream](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams), adding Adobe Analytics as a service pointing to the desired report suite.
6. [Install the SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) on your mobile app.

>[!IMPORTANT]
>
>An Adobe Analytics extension is also available in the Data Collection UI. If you install this extension, you do not take advantage of XDM or the Edge Network.
