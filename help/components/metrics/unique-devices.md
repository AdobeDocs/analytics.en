---
title: Unique devices
description: The number of unique devices.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
---
# Unique devices

The 'Unique devices' metric is a [Cross-device analytics](../cda/overview.md) metric representing the total number of unique **un**identified devices (devices that generated anonymous hits) + total number of unique visitors identified per device.

* Please note that this metric is not equal to the Unique Visitors from Analytics.

* *Example*: If device1 is shared by 3 different accounts that generated events in the chosen reporting window, this will reflect as 3 different (virtual) devices in the reporting engine (to keep a positive compression in the shareable devices use-cases). In comparison, Unique Visitors traditional metric would count this as 1 unique device (visitor).

In other words, for each device we count all its distinct person attributions, plus the unidentified state if the case (if any anonymous non-stitched hits come from that device).
Summing up these values obtained from all devices, we get the value of *Unique Devices* metric. 
 
Below you can see a more descriptive example of how Unique Devices and People metrics work:

* Bob noticed an ad on his phone with Adobe Photoshop, once he clicks on it the ad will redirect Bob on Adobe homepage
	* one device one person
* Bob is browsing quite a bit and at a point he decides to buy Photoshop, because Bob has no card on his phone he will go on his laptop
* Once Bob is on the laptop he will create an account and then he will buy photoshop
	* two devices one person
* Bob also logs in on his phone at a later time to check his order.
	* two devices one person
* Bob’s wife, Alice has no laptop so she will use Bob’s laptop to play with Photoshop but using her account
	* two devices two persons
* Bob’s brother, Charles will also login using Bob’s laptop on his account
	* two devices three persons

So at the end of this story, we would "normally" expect 2 unique devices and 3 people.
However in CDA world, for the entire timeframe we would get in the report:
* **5 unique devices**: 1 for unidentified person (for unauthenticated Bob)  + 2 for Bob + 1 for Alice + 1 for Charles
* **4 [People](people.md)**: 1 [Unidentified People](unidentified-people.md) + 3 [Identified People](identified-people.md).

![Unique Devices Count](/help/components/metrics/assets/Unique_Devices_Count.png)