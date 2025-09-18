---
description: Learn about the benefits and constraints of using Timestamps Optional setting.
keywords: Analytics Implementation
title: Timestamps Optional
topic-fix: Developer and implementation
feature: Implementation Basics
exl-id: c6a232d1-d7ce-4f21-9e8a-45703992bc6e
---
# Timestamps Optional

Learn about the benefits and constraints of using Timestamps Optional setting.

<!-- Hide video as it is not adding a lot according to feedback from customer in feedback report January 2025.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Timestamps Optional](https://video.tv.adobe.com/v/335740?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]
-->


Timestamps Optional is the default setting for all new report suites.

* Mix timestamped and non-timestamped data in the same global report suite.
* Send timestamped data from a mobile app to a global report suite.
* Upgrade apps to employ timestamps without having to create a new report suite.

>[!NOTE]
>
>Timestamps Optional is the default setting for all new report suites generated from a template. New report suites copied from an existing report suite will inherit settings from the original.

See [Timestamps Optional](/help/technotes/timestamps-optional.md) for additional setup information.

## Timestamps Optional: Integrate timestamped and non-timestamped data {#integrate}

Using the Timestamps Optional feature, you can combine non-timestamped data with timestamped data without incurring data loss. Offline data with timestamps generated from a mobile device can be combined with live, non-timestamped data from a web page—or integrated with data from any platform using a client-side timestamp call.

* **Timestamp data**. Client-side timestamp data is captured and sent directly with the device data using client-side timestamp variables: Javascript on a web page, or using a Mobile SDK call ( [!DNL offlineEnabled=true]) in a mobile app.
* **Non-timestamp data**. Adobe sets a timestamp on non-timestamped data in a report suite when the data hits the collection servers.

A report suite can have one of the following timestamp settings:

* Timestamps not allowed (setting visitorID supported)
* Timestamps required (setting visitorID not supported)
* Timestamps optional (setting visitorID supported but not on timestamped hits)

## About Timestamps Optional features {#features}

Timestamps Optional allows you to integrate and report across multiple report suites with or without client-side timestamps included. With Timestamps Optional you can update your app to employ timestamps while still using non-timestamped data from the previous app.

|In previous releases...|In addition...|
|--- |--- |
|Timestamped data could not be sent to a non-timestamped global report suite. Consequently, hit data sent from offline devices was dropped when adding to a non-timestamped report suite. <br/><br/>Consequently, hit data sent from offline data was dropped when adding to a non-timestamped report suite.|Updating an app to collect and use timestamps required you to employ a new report suite. <br/>You could not save to the existing report suite or integrate existing data when updating your app to use timestamps.|

**With Timestamps Optional**, you can integrate non-timestamped data from a live website with offline data from mobile devices, or update your non-timestamped app to a timestamped app.

## Combining data into a Global Report Suite {#combine}

Combining data into a global report suite can be done in multiple ways, including multi-suite tagging, Vista rules, and imported batch files from offline sources.

>[!IMPORTANT]
>
>Carefully plan the design for each component data set so the combination makes sense in a global report suite.

## Best practices when employing timestamps {#best-pratices}

The following are best practices and a few requirements and restrictions to be aware of when integrating timestamped with non-timestamped data.

* In general, timestamps for a given visitor or visit must arrive at Adobe in the correct chronological order.

  Out-of-order data can include late arriving data from offline data collection and late arriving hits, or out-of-sync clocks on offline mobile devices. Out-of-order data can negatively impact time calculations (such as time spent values), attribution (eVar persistence), visit number/visit counts, and pathing reports.

* Using timestamps when setting a [s.visitorID](/help/implement/vars/config-vars/visitorid.md) is not recommended. It can lead to out-of-order data.

* Hybrid apps composed of an app (timestamped, offline data) opening a web browser (non-timestamped, live data) should not use timestamps. It results in inaccurate reporting of the session.

  In addition, hybrid apps should not set a visitor ID.
