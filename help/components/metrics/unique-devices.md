---
title: Unique devices
description: The number of unique devices.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
---
# Unique devices

The 'Unique devices' metric is a [Cross-device analytics](../cda/overview.md) metric that counts the number of unique unidentified devices and unique virtual devices. Unidentified devices are devices that generated anonymous hits. Unique virtual devices are distinct people identified per device.

## How this metric is calculated

For each device, sum all distinct people tied to it (including anonymous if the device contains non-stitched hits).

Note that this metric is not equal to [Unique Visitors](unique-visitors.md) in non-CDA report suites. For example, a device is shared by 3 different accounts. If all 3 accounts visit your site in a reporting window, the resulting report would show 3 Unique Devices in CDA. The same data outside of CDA would show 1 Unique Visitor.

## Example

1. Sally arrives to your site on his phone through an ad, but is not logged in.
1. Sally wants to make a purchase, but would prefer to do it on the family computer because she is already logged in there. On the family computer, she makes a purchase.
1. The next day, she checks his order on his phone and authenticates there.
1. Bob's wife, Alice, browses your site while logged in to her account on the family computer.
1. Bob's brother, Charles, also browses your site while logged in to his account on the family computer.

![Unique Devices Count](/help/components/metrics/assets/Unique_Devices_Count.png)

Viewing this data in a CDA virtual report suite before [Replay](/help/components/cda/replay.md) potentially stitches unauthenticated hits would show:

* **5 unique devices**: 1 for unauthenticated Bob + 2 for Bob + 1 for Alice + 1 for Charles
* **4 [People](people.md)**: 1 [Unidentified People](unidentified-people.md) + 3 [Identified People](identified-people.md).
