---
description: Custom bot rules let you filter traffic based conditions you define.
seo-description: Custom bot rules let you filter traffic based conditions you define.
seo-title: Create a custom bot rule
solution: Analytics
subtopic: Bot rules
title: Create a custom bot rule
topic: Admin tools
uuid: abbc5c7e-912f-4660-a02b-0431a740ec70
---

# Create a custom bot rule

Custom bot rules let you filter traffic based conditions you define.

Custom bot rules are defined using the following condition types:

* User Agent 
* IP Address 
* IP Range

Multiple conditions can be defined for a single rule. Multiple conditions are matched using "or". For example, if you provide a value for User Agent and IP Address, the traffic is considered bot traffic if either condition is met.

## User Agent

A User Agent condition checks the user agent value to see if it **[!UICONTROL starts with]** or **[!UICONTROL contains]** the specified string. If **[!UICONTROL contains]** is selected, the substring is matched if it occurs anywhere in the user agent.

Optional values can be included in the **[!UICONTROL does not contain]** list to define values that the user agent must not contain for a successful match. Multiple values can be specified by including one value per line. If the user agent meets the criteria specified in the match string, but also contains a string on the does not contain list, it is not considered a match.

The **[!UICONTROL contains]** field is limited to 100 characters. The does not contain list is limited to 255 characters minus a separator character for each new line. (This is equal to the number of strings - 1. If you specify 4 *does not contain* strings, 3 separator characters are required.) All string matches are case-insensitive.

## IP Address (including wildcard matches)

Matches an IP address or multiple addresses in the same block using wildcards (&#42;). Provide the numeric values of the IP address you want to match. Substitute &#42; for any values you want to match using a wildcard. The following list contains examples of IP address match string:

```
10.10.10.1
10.10.10.*
```

## IP Address Range

Provide the start and end ranges of the IP addresses to match. Substitute &#42; for any values you want to match using a wildcard.

## Define a custom bot rule

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, select one or more report suites and click **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Click **[!UICONTROL Save]**. The change should take effect within 30 minutes.

>[!Note]
>The user interface allows for 500 rules to be manually defined. After this limit is reached, rules must be managed in bulk through the Import File and Export Bot Rules options. 
