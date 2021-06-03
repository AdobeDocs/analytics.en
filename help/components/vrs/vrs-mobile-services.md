---
description: The Adobe Mobile Services UI combines mobile app data from your Adobe Analytics report suites with the ability to send push notifications and generate in-app messages.
title: VRS support in Mobile Services
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
exl-id: 3082333a-514d-45c6-9432-da32bd27a2eb
---
# VRS support in Mobile Services

The Adobe Mobile Services UI combines mobile app data from your Adobe Analytics report suites with the ability to send push notifications and generate in-app messages.

## VRS support in Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

The Adobe Mobile Services UI combines mobile app data from your Adobe Analytics report suites with the ability to send push notifications and generate in-app messages.

Adobe Mobile Services supports virtual report suites. However, if you plan to create a virtual report suite with multiple apps and you plan to perform a messaging activity, you must specify the individual App-ID as a parameter. If you are creating a Push Message, the App-ID needs to be one of the parameters of the segment you are using. If you are creating an In-App Message, the App-ID needs to be one of the parameters of the Traits you establish for the message. If this is not done, the message will be sent/triggered to all users across all apps who meet the segment/trigger criteria.

For more details, see [Virtual Report Suites](https://experienceleague.adobe.com/docs/ mobile-services/using/manage-apps-ug/c-mob-vrs.html) in the Adobe Mobile Services documentation.
