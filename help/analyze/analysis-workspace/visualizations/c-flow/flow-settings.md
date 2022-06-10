---
description: Use the flow visualization in a Workspace project.
title: Flow settings
uuid: 99822765-1d4f-4c23-a787-b089089cb8d7
feature: Visualizations
role: User, Admin
exl-id: 12a358b4-4f8e-4201-9f97-5c07c91f301e
---
# Flow settings

| Setting | Description |
|--- |--- |
| Flow Container |<ul><li>Visit</li><li>Visitor</li></ul> Lets you switch between Visit and Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level (across visits), or constrain the analysis to a single visit.|
|Flow Options |<ul><li>Wrap Labels</li></ul> Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box.  Default = unchecked.<ul><li>Include Repeat Instances</li></ul> Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, e.g. Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc.|

## Right-click options

| Option | Description |
|--- |--- |
|Focus on this node|Change the focus to the selected node. The focus node appears at the center of the Flow diagram.|
|Start Over|Returns you to the Freeform diagram builder, where you can build a new Flow diagram.|
|Create Segment from this point in flow|Create a segment. This takes you into the Segment Builder, where you can configure the new segment.|
|Breakdown|Break the node down by available Dimensions, Metrics, or Time.|
|Trend|Create a trended diagram for the node.|
|Expand entire column|Expand a column to show all nodes. By default, only the top five nodes display.|
|Collapse entire column|Hide all nodes in a column.|
