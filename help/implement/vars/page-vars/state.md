---
title: State
description: Populate the 'Visitor State Report' in Reports and Analytics.
---

# state

>[!IMPORTANT] This variable is retired and not an available dimension in Analysis Workspace. Use the 'US States' dimension instead, which AppMeasurement automatically collects based on the location of the visitor.

In previous versions of Adobe Analytics, the `state` variable was used when visitors filled out shipping information on retail sites. It is functionally identical to a prop, but is not available in Analysis Workspace.

## State in Adobe Experience Platform Launch

You can set state either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL State] section.

You can set state to any string value or data element.

## s.state in AppMeasurement and Launch custom code editor

The `s.state` variable is a string that typically contains the state or province of the visitor. Full state names or two-letter codes are both valid. It has a maximum value of 50 bytes; longer values are truncated. Its default value is an empty string.

```js
s.state = "Utah";
```
