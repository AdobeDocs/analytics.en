---
description: Use the flow visualization in a Workspace project.
title: Configure a flow visualization
feature: Visualizations
role: User, Admin
---

# Configure a flow visualization

>[!NOTE]
>
>This new version of the [!UICONTROL Flow] visualization is currently in private beta.

Flow lets you track the exact journeys your customers are taking through your website or your app. It traces a path through your dimensions (and dimension items) or metrics. Every flow has a starting point and an endpoint, and a metric or dimension (or item) that you are tracking. 

The new [!UICONTROL flow] experience enhances your workflow in several ways:

* It allows for metrics to be tracked, in addition to dimensions and dimension items.
* It contains [!UICONTROL Advanced Settings] to let you further customize the [!UICONTROL flow].
* It lets you configure the [!UICONTROL flow] before building it.

![](assets/new-flow.png)

1. To start creating a flow diagram, add a blank panel to your project and click the visualizations icon in the left rail. Then drag the Flow visualization into the panel. Or drag the [!UICONTROL Flow] visualization into an existing project.

1. Anchor your Flow visualization using one of three options:

   * [!UICONTROL Starts with] (metrics, dimensions, or items), or
   * [!UICONTROL Contains] (dimensions, or items), or
   * [!UICONTROL Ends with] (metrics, dimensions, or items)

   Each of these categories is shown onscreen as a "drop zone." Drag items from the dimensions or metrics list and drop them into the desired drop zone.

   For example, let's assume that you want to trace everything that leads up to a checkout event. You would drag a checkout-related dimension or metric into the **[!UICONTROL Ends with]** drop zone. 

1. If you choose a metric, you also need to provide a [!UICONTROL Pathing Dimension], as shown here. The default is Page.

   ![](assets/pathing-dim.png)

1. (Optional) Click **[!UICONTROL Advanced Settings]** to configure Advanced Settings:

