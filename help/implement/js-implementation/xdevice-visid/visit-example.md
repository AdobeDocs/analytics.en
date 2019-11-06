---
description: Example containing a sample of server calls sent in a common customer interaction.
keywords: Analytics Implementation
seo-description: Example containing a sample of server calls sent in a common customer interaction.
seo-title: Example visit
solution: Analytics
subtopic: Visitors
title: Example visit
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
---

# Example visit

>[!IMPORTANT]
>
>This method of identifying visitors across devices is no longer recommended. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Example containing a sample of server calls sent in a common customer interaction.

| Server Call | Action | Visitor ID Cookie | Visitor ID Variable | Effective Visitor ID | Visit Page Number | Visit Number |
|--- |--- |--- |--- |--- |--- |--- |
|1|A visitor clicks a link in a marketing email and visits your site from home computer. This visitor has visited your site 7 other times in the past.|1|-|1|1|8|
|2-8|Visits 7 additional pages on your site.|1|-|1|2-8|8|
|9|Authenticates on home computer.|1|CID1|CID1|9 <br>This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.</br>|8|
|10|Visits 1 additional page.|1|CID1|CID1|10|8|
|11|Opens site from laptop at office. This visitor has not visited your site before using this device.|2|-|2|1|1|
|12|Authenticates on laptop.|2|CID1|CID1|1|9|
|13|Views 1 additional page.|2|CID1|CID1|2|9|
