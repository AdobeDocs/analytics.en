---
title: Visitor identification using the Web SDK JavaScript library
description: Correctly identify visitors when implementing the Web SDK JavaScript library.
---
# Visitor identification using the Web SDK JavaScript library

If your organization uses the Web SDK JavaScript library to send data to Adobe Analytics, minimal configuration is required for visitor identification. The Visitor ID service is baked in natively to the library, only requiring that you set **[!UICONTROL Edge Domain]** in the `configure` command. If this field is set to the desired value, visitor identification works without any additional configuration.
