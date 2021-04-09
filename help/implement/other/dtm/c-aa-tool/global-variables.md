---
description: Field descriptions and information about variables when using Dynamic Tag Management to deploy Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics
title: Global variables
uuid: d759320a-96ee-4073-b5fd-5257b7033003
exl-id: e78e9ff4-bfce-4fa0-8d53-fd33ed3052fd
---
# Global variables

Field descriptions and information about variables when using Dynamic Tag Management to deploy Adobe Analytics.

These variables fire on all page load rule beacons. You can accomplish the same effect by using a [Page-Load rule](/help/implement/other/dtm/c-rules/t-rules-page-conditions.md) set to fire on all pages. These variables might not fire in [Direct-Call](/help/implement/other/dtm/c-rules/t-rules-direct-conditions.md) and [Event-Based](/help/implement/other/dtm/c-rules/t-rules-event-conditions.md) rules.

## Global Variables - Field Descriptions {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Global Variables]** 

| Element | Description |
|--- |--- |
|Server|The predefined variable populates the  Servers dimension in Adobe Analytics. See [Server](../../../vars/page-vars/server.md).|
|eVars|[eVar variables](../../../vars/page-vars/evar.md) are used for building custom conversion reports.|
|Props|[Prop variables](../../../vars/page-vars/prop.md) are used for building custom traffic reports.|
|Dynamic Variable Prefix|A special prefix to the start of the value. The default prefix is "D=". See [Dynamic Variables](../../../vars/page-vars/dynamic-variables.md|
