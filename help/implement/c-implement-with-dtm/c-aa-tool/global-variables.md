---
description: Field descriptions and information about variables when using Dynamic Tag Management to deploy Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Global variables
uuid: d759320a-96ee-4073-b5fd-5257b7033003
---

# Global variables

Field descriptions and information about variables when using Dynamic Tag Management to deploy Adobe Analytics.

These variables fire on all page load rule beacons. You can accomplish the same effect by using a [Page-Load rule](/help/implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md) set to fire on all pages. These variables might not fire in [Direct-Call](/help/implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md) and [Event-Based](/help/implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md) rules.

## Global Variables - Field Descriptions {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Global Variables]** 

| Element | Description |
|--- |--- |
|Server|The predefined variable populates the  Servers dimension in Adobe Analytics. See [Page Variables](/help/implement/js-implementation/page-variables/page-variables.md)|
|eVars|[eVar variables](/help/implement/js-implementation/page-variables/evarn.md) are used for building custom conversion reports.|
|Props|[Prop variables](/help/implement/js-implementation/page-variables/propn.md) are used for building custom traffic reports.|
|Dynamic Variable Prefix|A special prefix to the start of the value. The default prefix is "D=". See [Dynamic Variables](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/dynvars-overview.html)|
