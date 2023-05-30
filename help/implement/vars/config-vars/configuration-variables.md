---
title: Configuration variables
description: Use configuration variables to help determine how data is collected.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
---
# Configuration variables overview

Configuration variables control the way data is captured and processed in reporting. They do not typically contain dimension or metric values.

## Setting configuration variables

In implementations using the Web SDK extension or Analytics extension, configuration variables are typically found in the extension's settings:

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under the extension.

In JavaScript implementations using `AppMeasurement.js`, configuration variables are typically set at the top of the JS file.

>[!IMPORTANT]
>
>Make sure that all configuration variables are set before calling a tracking method ([`t()`](../functions/t-method.md) or [`tl()`](../functions/tl-method.md)). Avoid setting configuration variables in the [`doPlugins()`](../functions/doplugins.md) function.
