---
title: Visitor identification using the Web SDK tag extension
description: Correctly identify visitors when implementing the Web SDK tag extension.
---
# Visitor identification using the Web SDK tag extension

The Web SDK tag extension in Adobe Experience Platform Data Collection empowers organizations to implement the Web SDK using a tag management interface. Advanced scenarios like cross-domain ID sharing and visitor profile migration are easily configured through extension rules and actions. Using the Web SDK future-proofs your implementation and supports seamless upgrades to Customer Journey Analytics.

Since the Visitor ID Service is baked in natively to the tag extension, it only requires that you set **[!UICONTROL Edge Domain]** to the desired value. If this field is set correctly, visitor identification works without any additional configuration.

>[!NOTE]
>
>Do not include the Visitor ID Service tag extension if use the Web SDK tag extension. The Visitor ID Service tag extension is only required if you use the [Adobe Analytics extension](analytics-extension.md).
