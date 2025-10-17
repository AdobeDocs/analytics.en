---
title: Visitor identification using the Web SDK tag extension
description: Correctly identify visitors when implementing the Web SDK tag extension.
---
# Visitor identification using the Web SDK tag extension

If your organization uses the Web SDK tag extension to send data to Adobe Analytics, minimal configuration is required for visitor identification. The Visitor ID service is baked in natively to the tag extension, only requiring that you set **[!UICONTROL Edge Domain]** when configuring the tag extension. If this field is set to the desired value, visitor identification works without any additional configuration.

>[!NOTE]
>
>Do not include the Visitor ID Service tag extension if use the Web SDK tag extension. The Visitor ID Service tag extension is only required if you use the [Adobe Analytics extension](analytics-extension.md).
