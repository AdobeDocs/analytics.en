---
title: Configuration variables
description: Use configuration variables to help determine how data is collected.
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
---
# Configuration variables overview

Configuration variables control the way data is captured and processed in reporting. They do not typically contain dimension or metric values.

## Setting configuration variables

In JavaScript implementations using `AppMeasurement.js`, configuration variables are typically set at the top of the JS file.

In implementations using Adobe Experience Platform tags, configuration variables are typically found by configuring the Adobe Analytics extension:

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the property that you want to edit.
1. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT]
>
>Make sure all configuration variables are set before calling a tracking method ([`t()`](../functions/t-method.md) or [`tl()`](../functions/tl-method.md)). Avoid setting configuration variables in the [`doPlugins()`](../functions/doplugins.md) function.
