---
description: Event serialization is the process of implementing measures to prevent duplicate events from entering Analytics reporting. This can commonly occur when a user refreshes the page multiple times, navigates to a certain page multiple times, or saves the web page to their computer (for example, if a customer saves a purchase confirmation page to their computer, every time they view it orders and revenue would be counted again if event serialization was not in place).
keywords: Analytics Implementation
seo-description: Event serialization is the process of implementing measures to prevent duplicate events from entering Analytics reporting. This can commonly occur when a user refreshes the page multiple times, navigates to a certain page multiple times, or saves the web page to their computer (for example, if a customer saves a purchase confirmation page to their computer, every time they view it orders and revenue would be counted again if event serialization was not in place).
seo-title: Event serialization overview
solution: Analytics
title: Event serialization overview
topic: Developer and implementation
uuid: 8c7883bb-5ba4-4440-af80-c0d15867570c
index: y
internal: n
snippet: y
---

# Event serialization overview

Event serialization is the process of implementing measures to prevent duplicate events from entering Analytics reporting. This can commonly occur when a user refreshes the page multiple times, navigates to a certain page multiple times, or saves the web page to their computer (for example, if a customer saves a purchase confirmation page to their computer, every time they view it orders and revenue would be counted again if event serialization was not in place).

[!UICONTROL Event serialization] is useful in the following instances:

* A page may be reloaded or refreshed and repeatedly send an event. [!UICONTROL Event serialization] prevents events from being recounted by using a serial number for each event. 
* The user saves the page to his/her machine for later review. This scenario is quite common on purchase confirmation pages to review purchase receipts. [!UICONTROL Event serialization] prevents the subsequent page reloads from re-counting the events.

>[!NOTE]
>
>Data Sources does not support event serialization or de-duplication.

This document describes the process used to implement [!UICONTROL Event serialization] for [!UICONTROL conversion] and [!UICONTROL custom] events. To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** > **[!UICONTROL Report Suite]** > **[!UICONTROL [select report suite]]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Success Events]** . Then select which events you want recorded in the [!UICONTROL Unique Event Recording] column.

## Default Behavior {#section_892BB2BEFC434B69869D4504A8B54308}

The default behavior is to count each instance of an event. An event is set for each [!UICONTROL pageview]that is counted, even on page reloads or page refreshes. The [!UICONTROL s.purchaseID] variable is used in order to uniquely identify each order (purchase). This allows a user to reload the order page without recounting the order, revenue, or products. A similar feature is available for all events. This includes pre-defined events such as [!UICONTROL prodView] and [!UICONTROL scCheckout], as well as all custom events.

<!-- 

event_serialization_impl.xml

 -->

To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** > **[!UICONTROL Report Suite]** > **[!UICONTROL [select report suite]]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Success Events]** . Then select which events you want recorded in the [!UICONTROL Unique Event Recording] column. There are three different settings an event can be set to.

**Always record event**: This is the default behavior of all events when initially enabled. All events included in image requests will be sent directly to Analytics, including page reloads.

**Record once per visit**: An event with this setting enabled will only track the first instance of that event in a given visit. Once a new visit starts, each event with this setting enabled can be tracked again. This is an effective way to mitigate duplicate events via browser refreshes.

**Use event ID**: This setting allows the capability to associate each event with a unique ID. If Analytics sees an eventID it has already seen before with that variable, it will not be counted in reporting.

The only event that cannot have event serialization enabled is the purchase event, as this uses the s.purchaseID variable. All other eCommerce events and custom events can have these settings enabled.

* Use a unique identifier to let an event fire once per unique ID. 
* Send multiple events, then use configure Analytics to let an event fire once per visit.

To implement [!UICONTROL Event serialization], provide a unique ID for the event, for example event1:1234ABCD.

## Event Serialization - Once per Unique ID {#section_8806E48B497546F5A335383FB8627694}

Once [!UICONTROL Event serialization] is implemented, and [!DNL Analytics] receives a duplicate number, it ignores the event. An event is counted only once per unique value. If the number is unique, another event instance is counted, as shown in the following example: 

|  User Name  | Description  | Event Syntax  | Analytics Total Event1 Count  |
|---|---|---|---|
|  John  | User views page for the first time.  | event1:1000  | 1  |
|  John  | User reloads the page (a form submit may fail, and cause the page to reload).  | event1:1000  | 1  |
|  Stacy  | User views page for the first time.  | event1:1001  | 2  |
|  Stacy  | User reloads the page (a form submit may fail, and cause the page to reload).  | event1:1001  | 2  |
|  Jill  | User views page for the first time, enters information correctly, and moves on to next page.  | event1:1002  | 3  |
|  Jamie  | User views page for the first time  | event1  | 4  |
|  Jamie  | User forgets to fill in the last name field on the form. The form is displayed again with the missing information highlighted.  | event1  | 5  |

Note the following when selecting serialization IDs:

* Serialization IDs must be 20 characters or less. 
* Serialization IDs must be alphanumeric characters. 
* Serialization IDs are separate for each success event. Therefore, you can use the same ID for multiple success events if needed, just not for the same success event. 
* Serialization IDs are tied to the report suite, so if you are using multi-suite tagging to send data to multiple report suites, keep this in mind. 
* Serialization IDs never expire, so even if the same ID is used years later, the success event will not be counted again. 
* Cookie deletion does not prevent Event ID serialization because serialization IDs are stored on Adobe servers and are not cookie-based. 
* The one success event with which it is not possible to use Event ID serialization is the Purchase event, which uses a special s.purchaseID variable for serialization.

## Event Serialization - Once per Visit {#section_C919D44F321A47FBBF043D0C57A2A050}

[!DNL Analytics] offers a feature to let an event only fire once per visit.

This can be enabled from the UI:  **[!UICONTROL Admin]** > **[!UICONTROL Report Suite]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]** . 
