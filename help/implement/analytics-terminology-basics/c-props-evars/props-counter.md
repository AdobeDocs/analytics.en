---
description: A counter stores (and sometimes displays) the number of times a particular event or process has occurred.
keywords: Analytics Implementation;props;s.prop;custom traffic;counters
solution: Analytics
title: Using props as counters
topic: Developer and implementation
uuid: ab83bd7e-10d9-49f9-b9e7-c50397e95c17
---

# Using props as counters

A counter stores (and sometimes displays) the number of times a particular event or process has occurred.

You can use a prop to count the number of times an event occurs. For example, you want to track the use of the Real Player vs. the Windows Media Player on your site. Each page contains [!UICONTROL Code to Paste], in which you can see [!UICONTROL s.prop] variables. Use [!UICONTROL s.prop] 1 to track the players. For page A, enter a value in [!UICONTROL s.prop]1 to represent Real Player.

```js
s.prop1="RealPlayer"
```

For page B, enter a similar value in [!UICONTROL s.prop]1 for Windows Media Player, as shown below.

```js
s.prop1="WindowsMP"
```

> [!NOTE] Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

As visitors come to your site and visit the pages containing the Real Player or Windows Media Player, [!DNL Analytics] is able to segment the users based on which pages they visited. The [!UICONTROL Custom Traffic] report then shows the number of visits to each page.

> [!NOTE] The name of the [!UICONTROL Custom Traffic] report can be customized. For example, the [!UICONTROL Custom Traffic] report can be renamed to "Player Types Report."

