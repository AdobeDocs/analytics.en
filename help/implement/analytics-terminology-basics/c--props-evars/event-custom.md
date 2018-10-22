---
description: Custom events let you define the success type that you want to track.
keywords: Analytics Implementation;custom event
seo-description: Custom events let you define the success type that you want to track.
seo-title: What is a custom event?
solution: Analytics
title: What is a custom event?
topic: Developer and implementation
uuid: 2e5f10e4-0a9b-4022-8bbc-fca223229f82
index: y
internal: n
snippet: y
---

# What is a custom event?

Custom events let you define the success type that you want to track.

Although similar to [!UICONTROL predefined] events, [!UICONTROL custom] events let you define your own success metric. For example, if you have a newsletter, your success event could be "Registration." Clearly, "Registration" is not part of the [!UICONTROL predefined] events. By using a [!UICONTROL custom] event, you can track the number of visitors who register for your newsletter. [!UICONTROL Custom] events follow the standard syntax shown below.

```js
s.events="event3"
```

The code above shows how to assign an event to the *`events`* variable. If you do not modify the event name in the interface, then "event3" would display in the interface.

By default, success events are configured as "counter" events. Counter events count the number of times a success event is set. Some success event uses require an event be incremented by some custom amount. These events can be set either as " [!UICONTROL numeric]" events or " [!UICONTROL currency]" events. You can change the event type using Admin Console. 
