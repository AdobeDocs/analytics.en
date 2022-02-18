---
description: Data sources provides two additional ways to integrate events that occur offline to your online data.
subtopic: Data sources
title: Transaction and customer integration
topic-fix: Developer and implementation
feature: Data Sources
exl-id: d4e4388b-6449-4fef-a94d-01b3a52c2190
---
# Transaction and customer integration

Data Sources provides two additional ways to integrate events that occur offline to your online data.

* [Enable Transaction ID Recording](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) 
* [Transaction Integration](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_B3F281CEFF9B47E9A07F9851D61D415D) 
* [Customer Integration](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_9F4AAD710D2543BDA834090A98115FBF)

These integrations associate offline data with a specific online transaction or with an online visitor.

## Enable Transaction ID Recording {#section_30D6D47AEC0F4A36B87EBFE4C858F20C}

The Transaction ID can be enabled/disabled from the UI, without the involvement of ClientCare:

Go to **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**.

<!-- 

<p>When contacting Customer Care, be prepared to provide the following information: </p> 
<ul id="ul_C425C7A074484650AFCCF0425E8E3F47"> 
 <li id="li_7640C0C4DF0C49749A3C37E5461DC22F">Report Suite ID of the data source for which you need transaction ID recording enabled. <p>In Data Sources, the report suite ID is the first part of the login appended by a random number that identifies the specific data source that was set up. For example, <code> RSID-drmossdev5 Login-drmossdev5_0001343430</code>. </p> </li> 
 <li id="li_4FB0E3EC7BE94A2DBEE9063365A71C9C">The Transaction ID expiration window (described in <a href="/help/import/c-data-sources/datasrc-tid-visitor-profile.md"  > Transaction ID and Visitor Profiles</a>). By default this is 90 days, but it can be extended to up to 2 years. </li> 
</ul>

 -->

To see if Transaction ID Recording is enabled, navigate to **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data sources]**.

![](assets/transaction-ID-recording-active.png)

The [!UICONTROL Manage] tab displays the status of Transaction ID Recording.

## Customer Integration {#section_9F4AAD710D2543BDA834090A98115FBF}

Customer IDs are used to specify a customer's offline activity and tie it to online activity. These should be used when:

* A customer ID is populated in the *`visitorID`* variable.
* There is no designated point where customer activity moves offline, such as a lead submission or purchase.

To configure this type of data source, see [Visitor ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)

## Transaction Integration {#section_B3F281CEFF9B47E9A07F9851D61D415D}

Transaction IDs are used to record the state of a visitor at a point in time. These should be used when there is a point in time when customers typically move their experience from online to offline, such as:

* Submits a lead for a salesman to contact the customer.
* Makes an online purchase, which might be later returned in store.
* Purchases a product for which they might later call for support.

The customer is often anonymous when they move from online to offline.

Transaction ID events are not included in Visit Participation metrics (those shown in marketing reports). This is because the transaction ID data is not associated with a visit (because the offline event is usually not part of the online event), but it is associated with the visitor.

See [Transaction ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md).
