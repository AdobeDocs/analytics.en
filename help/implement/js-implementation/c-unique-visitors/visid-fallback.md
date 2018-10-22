---
description: If other visitor ID methods fail, Adobe sets a fallback cookie or uses a combination of IP address and user agent to identify the visitor.
keywords: Analytics Implementation
seo-description: If other visitor ID methods fail, Adobe sets a fallback cookie or uses a combination of IP address and user agent to identify the visitor.
seo-title: Fallback ID methods
solution: Analytics
title: Fallback ID methods
topic: Developer and implementation
uuid: af267a65-fab6-42e5-9671-e4cdcd0e30cc
index: y
internal: n
snippet: y
---

# Fallback ID methods

If other visitor ID methods fail, Adobe sets a fallback cookie or uses a combination of IP address and user agent to identify the visitor.

## Fallback Visitor Identification Method {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe’s data collection servers (called `s_vi`). Previously, if a cookie could not be set, visitors were identified using a combination of the IP address and user agent string during data collection.

With this update, if the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2 year expiration and is used as the fallback identification method going forward. This change should result in increased accuracy in visit and visitor counts in situations where the primary cookie ( `AMCV_` or `s_vi`) cannot be set.

Visits total includes all visitors that are identified by the `s_vi` cookie or by using a fallback method.

## IP Address, User Agent, Gateway IP Address {#section_104819D74C594ECE879144FCC5DEF4BF}

. If the `AMCV_` or `s_vi` and the `s_fid` cookies cannot be set, visitors are identified using a combination of IP address and User Agent. 
