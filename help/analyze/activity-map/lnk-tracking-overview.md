---
description: Activity Map tracks links with a more robust algorithm that 
title: Robust link tracking
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
feature: Activity Map
role: User, Admin
exl-id: 1f077234-ff88-46ce-a931-2d21d68042b0
---
# Robust link tracking

Activity Map tracks links with a more robust algorithm that:

* Includes the tracking of page regions to avoid cases of the same link being confused across different devices because the link shows up in different positions on the page; 
* Ensures link uniqueness, meaning that distinct links cannot be mistaken for one because of issues with LinkID or across different browser makes.

For more on link tracking in Activity Map, go [here](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## How Activity Map link tracking may collect PII Data {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION]
>
>By turning on Activity Map tracking, you may be collecting personally identifiable information (PII) data. This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.

Here are some known cases where PII data might be collected using Activity Map Tracking:

* `Mailto` links. A mailto link is a type of HTML link that activates the default mail client on the computer for sending an e-mail.
* `User ID` links that may show up in the header/footer of a website once the user has logged in.
* For financial institutions, the account number may be shown as a link. Clicking it will collect the text of the link.
* Healthcare websites may also have PII data shown as links. Clicking these links will collect the text of the link, thereby collecting PII data.
