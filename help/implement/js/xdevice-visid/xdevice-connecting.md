---
description: Cross-device visitor identification helps you connect visitors across multiple devices. Cross-device visitor identification uses the visitor ID variable, s.visitorID, to associate a user across devices.
keywords: Analytics Implementation
subtopic: Visitors
title: Connect users across devices
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
---
# Connect users across devices

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. See [Cross-Device Analytics](/help/components/cda/overview.md) in the Components user guide.

Cross-device visitor identification helps you connect visitors across multiple devices. Cross-device visitor identification uses the `visitorID` variable to associate a user across devices. The `visitorID` variable takes the highest priority when identifying unique visitors.

When you send a hit with a custom visitor ID, Adobe checks for any visitor profiles that have a matching visitor ID. If one exists, the visitor profile already in the system is used from that point forward and the previous visitor profile is no longer used.

Setting the `visitorID` variable is typically set after authentication, or after a visitor performs some other action that allows you to uniquely identify them independently of the device that is used. Effective identifiers include a hash of their username, email address, or an internal ID that does not contain any personally identifiable information.

After the customer signs in from each device, they are all tied to the same user profile. If the visitor later signs out on a device, they continue to belong to the same visitor profile because Adobe recognizes that the browser cookie on each device belongs to the same visitor profile. Adobe recommends using the `visitorID` variable whenever possible in case the browser cookie is deleted.

## Limitations

Using your own custom visitor ID's gives you more control over how visitors are identified, but it comes with its limitations.

* **Visitor deduplication is not retroactive**: If a visitor accesses your site for the first time, then authenticates, two unique visitors are counted. One unique visitor counts for the generic Analytics ID automatically generated, and another counts for the custom visitor ID when they log in. This duplication of unique visitors is present for every time a visitor uses a new device or clears their cookies.
* **Incompatibility with the Experience Cloud ID Service**: Since the introduction of cross-device visitor identification, Adobe has released more powerful and more reliable ways to track visitors across devices. These new methods of identification are not compatible with the custom visitor ID override. If you plan to use the ID Service, Cross-Device Analytics (CDA), or the Device co-op, Adobe strongly recommends against using the `visitorID` variable.
