---
title: Functions and methods
description: Learn how you can use the functions and methods that Adobe offers in your implementation.
feature: Variables
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
---
# Functions and methods

Adobe offers several functions and methods that you can use in your implementation. When you reference these functions or methods, they perform common tasks with a single line of code.

Some of these single lines of code belong to the following categories:

* **Tracking calls**: The most common methods, and vital in many implementations. They include the [`t()`](t-method.md) and [`tl()`](tl-method.md) methods.
* **AppMeasurement utilities**: In previous versions of AppMeasurement, implementations had to write their own code to perform these tasks. Adobe provides these utility methods to streamline these common tasks. AppMeasurement utilities include [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md), and [`Util.getQueryParam()`](util-getqueryparam.md).
* **Register functions**: You can write your own functions and have AppMeasurement automatically execute them before or after sending a tracking call to Adobe. Variables that fall under this category are [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md), and [`registerPostTrackCallback()`](registerposttrackcallback.md).
