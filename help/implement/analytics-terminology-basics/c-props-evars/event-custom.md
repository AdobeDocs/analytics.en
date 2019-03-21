---
description: Custom events let you define the success type that you want to track.
keywords: Analytics Implementation;custom event
seo-description: Custom events let you define the success type that you want to track.
seo-title: What is a custom event?
solution: Analytics
title: What is a custom event?
topic: Developer and implementation
uuid: 8e78ba04-9b4c-4566-980c-c24dd9d82236
---

# What is a custom event?

Custom events let you define the success type that you want to track.

Although similar to [!UICONTROL predefined] events, [!UICONTROL custom] events let you define your own success metric. For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. By using a [!UICONTROL custom] event, you can track the number of visitors who register for your newsletter. [!UICONTROL Custom] events follow the standard syntax shown below.

```js
s.events="event3"
```

The code above shows how to assign an event to the _events_ variable. If you do not modify the event name in the interface, _event3_ would display in the interface.

By default, success events are configured as _counter_ events. Counter events count the number of times a success event is set. Some success event uses require an event be incremented by a custom amount. These events can be set either as _numeric_ events or _currency_ events. You can change the event type in Admin Console.
