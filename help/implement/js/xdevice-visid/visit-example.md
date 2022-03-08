---
description: Example containing a sample of server calls sent in a common customer interaction.
keywords: Analytics Implementation
subtopic: Visitors
title: Cross-device visitor identification example
feature: Implementation Basics
exl-id: c68bb745-29de-48e3-8731-d714503a2447
---
# Cross-device visitor identification example

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. See [Cross-Device Analytics](/help/components/cda/overview.md) in the Components user guide.

The following example illustrates how cross-device visitor identifcation works using a sample of server calls sent in a common customer interaction.

| Server Call | Action | Visitor ID Cookie | Visitor ID Variable | Effective Visitor ID | Visit Page Number | Visit Number |
|--- |--- |--- |--- |--- |--- |--- |
|1|A visitor clicks a link in a marketing email and visits your site from home computer. This visitor has visited your site 7 other times in the past.|1|-|1|1|8|
|2-8|Visits 7 additional pages on your site.|1|-|1|2-8|8|
|9|Authenticates on home computer.|1|CID1|CID1|9 <br>(This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.)|8|
|10|Visits 1 additional page.|1|CID1|CID1|10|8|
|11|Opens site from laptop at office. This visitor has not visited your site before using this device.|2|-|2|1|1|
|12|Authenticates on laptop.|2|CID1|CID1|1|9|
|13|Views 1 additional page.|2|CID1|CID1|2|9|

## Visit counting

Analytics counts a visit each time it sees a hit with a visit page number equal to 1.

Using the above table, a new visit was counted 4 times: on hits 1, 9, 11, and 12.

## Visitor counting

Analytics counts each unique effective visitor ID as a unique visitor.

Using the above table, a new visitor was counted 3 times: on hits 1, 9, and 10.

When you use cross-device visitor identification, the number of unique visitors you see can increase. The visitor can be counted twice on the same visit: once for the initial visit and again after the user is authenticated.

![](assets/visitors.png)

After the initial association, visit counts return to normal because the visitor is associated through their browser cookie. If the visitor later views your site and then authenticates, the visitor count is not inflated because the effective visitor ID doesn't change after authentication.

![](assets/visitors_2.png)

Make sure that you are as consistent as possible when identifying unique visitors. For example, always use the `visitorID` variable when the user is authenticated.
