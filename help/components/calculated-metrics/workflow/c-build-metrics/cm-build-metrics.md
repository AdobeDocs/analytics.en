---
description: Learn about the calculated metrics builder that provides a canvas to drag and drop dimensions, metrics, segments, and functions to create custom metrics based on container hierarchy logic, rules, and operators.
title: Build Metrics
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
TQID: https://experienceleague.adobe.com/ds8aD51DynOEJ7uYZ5Id-kTng2JPN4nZYuMTaKj-ZvE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
    internal-label: Workspace projects
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Build calculated metrics {#build-metrics}

Adobe Analytics provides a canvas to drag and drop dimensions, metrics, segments, and functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex calculated metrics.

You can use the calculated metric builder to create or edit calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. Alternatively, you can quickly create a calculated metric that is available only for the project where it was created, as described in [Create calculated metrics for a single project](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

[Create a calculated metric](../cm-workflow.md) describes the different options available to create a new calculated metric.

## Areas of the calculated metrics builder

The **[!UICONTROL Calculated metric builder]** dialog is used to create new or edit existing calculated metrics. The dialog is titled **[!UICONTROL New calculated metric]** or **[!UICONTROL Edit calculated metric]** for metrics that you create or manage from the [[!UICONTROL Calculated metrics] manager](../cm-manager.md).

>[!BEGINTABS]

>[!TAB Calculated metric builder] 

![Calculated metric details window showing fields and options described in the next section.](assets/calculated-metric-builder.png)

>[!TAB Create or Edit calculated metric] 

![Calculated metric details window showing fields and options described in the next section.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Specify the following details (![Required](/help/assets/icons/Required.svg) is required):

   | Element | Description |
   | --- | --- |
   | **[!UICONTROL Report suite]** | You can select the report suite for the calculated metric.  The calculated metric you define is available in Workspace projects based on the selected report suite. |
   | **[!UICONTROL Project-only metric]** | An info box appears at the top of this dialog when you edit a calculated metric that was created for a single project, as described in [Create calculated metrics for a single project](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>If you want to make this calculated metric available for all projects, select the option, **[!UICONTROL Make this metric available to all your projects and add it to your component list]**.</p> |
   | **[!UICONTROL Title]** ![Required](/help/assets/icons/Required.svg) | Name the calculated metric, for example, `Conversion Rate`. |
   | **[!UICONTROL Description]** | Provide a description for the segment, for example, `Calculated metric to define the conversion rate.` There is no need to describe the formula for the calculated metric as the formula is already automatically available in [!UICONTROL Summary]. |
   | **[!UICONTROL Format]** | Select a format for the calculated metric: You can select between **[!UICONTROL Decimal]**, **[!UICONTROL Time]**, **[!UICONTROL Percent]**, and **[!UICONTROL Currency]**. |
   | **[!UICONTROL Decimal places]** | Specify the number of decimal places for the format selected. Only enabled when the format selected is Decimal, Currency, and Percent. |
   | **[!UICONTROL Show upward trend as]** | Specify whether an upward trend of the calculated metric displays as ▲ **[!UICONTROL Good (Green)]** or as ▼ **[!UICONTROL Bad (Red)]**. |
   | **[!UICONTROL Currency]**  | Specify the currency of the calculated metric. Only enabled when format selected is Currency. |
   | **[!UICONTROL Tags]**| Organize the calculated metric by creating or applying one or more tags. Start typing to find existing tags you can select. Or press **[!UICONTROL ENTER]** to add a new tag. Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove a tag. |
   | **[!UICONTROL Preview]** | The preview covers the last 90 days and is a way to gauge whether you have defined your metric correctly. |
   | **[!UICONTROL Summary]** | Displays a summary of the definition of the calculated metric. <br/>For example:  ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**. |
   | **[!UICONTROL Definition]** ![Required](/help/assets/icons/Required.svg)| Define your segment using the [Definition builder](#definition-builder). |

1. To verify whether your calculated metric definition is correct, use the constantly updated **[!UICONTROL Preview]** of the results of the calculated metric. The **[!UICONTROL Preview]** covers the last 90 days and evaluates the definition of your calculated metric continuously.
   
   The **[!UICONTROL Product compatibility]** indicates the compatibility of the calculated metric with Adobe Analytics functionalities. See [Metric compatibility](/help/components/calculated-metrics/cm-compatibility.md) for more information. 

1. Select:
   * **[!UICONTROL Save]** to save the calculated metric.
   * **[!UICONTROL Save As]** to save a copy of the calculated metric. 
   * **[!UICONTROL Cancel]** to cancel any changes you made to the calculated metric or cancel the creation of a new calculated metric.


## Definition builder

You use the Definition builder to drag and drop dimensions, metrics, segments, and functions to create custom metrics based on container hierarchy logic, rules, and operators. In that construction, you can use standard metrics, Adobe defined metrics, calculated metrics, segments, dimensions and functions. All these components are available from the component panel in the Calculated metric builder. Furthermore, you can use operators and containers in the definition.

![Create calculated metric](assets/create-calculated-metric.gif)

Only metrics are defined as singular components in the **[!UICONTROL Definition]** area. All other components are defined as a container, wrapping metrics or other containers. See [Containers](#containers) for more information.

### Metrics

To add a metric:

* Drag and drop an ![Events](/help/assets/icons/Event.svg) **[!UICONTROL Metrics]** component from the components panel onto **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. You can use the ![Search](/help/assets/icons/Search.svg) in the components bar to search for specific components.

When you use a calculated metric as part of your definition, the calculated metric is expanded.

To modify a metric:

1. Select ![Setting](/help/assets/icons/Setting.svg) in a metric component in the **[!UICONTROL Definition]** area.
1. In the popup dialog you can define the type of metric and an attribution model. See [Metric type and Attribution](m-metric-type-alloc.md).

To delete a metric:

* Select ![Close](/help/assets/icons/Close.svg) in the metric.

### Operators

Operators let you specify the operator between components or containers. Operators appear automatically between

* two or more metrics in a container, 
* two or more containers in a container, 
* one or more metrics and one or more containers in a container. 
 
You can select:

| Symbol | Operator |
|:---:|---|
| ![Divide](/help/assets/icons/Divide.svg) | Divide (default) |
| ![Close](/help/assets/icons/Close.svg) | Multiply |
| ![Remove](/help/assets/icons/Remove.svg) | Subtract |
| ![Add](/help/assets/icons/Add.svg) | Add |

### Static number

You can add a static number to your calculated metric definition. To add a static number:

* Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** from within a container.
* Select **[!UICONTROL Static number]**. A static number container appears. 
* Select [!UICONTROL *Click to add a value*] and type a value.


### Containers

You add dimensions, segments and functions as containers to a calculated metric definition. You can also add a generic container. Containers function like a math expression and determine the order of operations. Anything within a container gets processed before the next component or container.


#### Segment container

You use the concept of a segment container to create a [segmented metric](metrics-with-segments.md). You can construct a segment container using a segment, or using a segment you create from a dimension.

* To add a segment container from a dimension:

  1. Drag and drop a ![Dimensions](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensions]** component from the components panel onto **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. You can use the ![Search](/help/assets/icons/Search.svg) in the components bar to search for specific components.
  1. In the **[!UICONTROL Create Segment from Dimension]** popup, define the condition for the segment. Select from the list of operators and select a value or enter a value. For example, **[!UICONTROL Month]** **[!UICONTROL equals]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
  1. Select **[!UICONTROL Done]**. A segment container is added to the **[!UICONTROL Definition]**. 


* To add a segment container from a segment, you can use:

  * Drag and drop a ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** component from the components panel onto **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. You can use the ![Search](/help/assets/icons/Search.svg) in the components bar to search for specific segments.
    Automatically a segment container is added to the **[!UICONTROL Definition]**, using the name of the segment.

  * Drag and drop a ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** component from the components panel onto a generic container. The container is modified into a segment container.

  * Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** from within a container:

    1. Select **[!UICONTROL Segment]**. A segment container is added to the **[!UICONTROL Definition]**.
    1. In the new segment container, select a segment from the [!UICONTROL *Select...*] drop-down menu.

  >[!TIP]
  >
  >You can add more than one segment to a container. 

  The segments in the container are named after the segment component. For example, ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web sessions]**. Select ![InfoOutline](/help/assets/icons/InfoOutline.svg) to display a popup with details on the segment. In the popup, select ![Edit](/help/assets/icons/Edit.svg) to edit the segment definition.

To remove a segment from a container:

* Select ![Close](/help/assets/icons/Close.svg) next to the segment name.

See [Segmented metrics](metrics-with-segments.md) for more details and examples.

#### Function container

To add a function container, you can use:

* Drag and drop:

  1. Drag and drop a ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]** component from the components panel onto **[!UICONTROL Drag and drop metrics, dimensions, dimension items, segments, and/or functions here]**. You can use the ![Search](/help/assets/icons/Search.svg) in the components bar to search for specific functions.
  1. Automatically a function container is added to the **[!UICONTROL Definition]** using the name of the function. 

* Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** from within a container:

  1. Select **[!UICONTROL Function]**.
  1. In the container, select a function from the [!UICONTROL *Select...*] drop-down menu.

The function container is named after the function component. For example, ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (metric)]**. Select ![InfoOutline](/help/assets/icons/InfoOutline.svg) to display a popup with details on the function. Select **[!UICONTROL Learn more]** for more information on the function. 

See [Use functions](cm-using-functions.md) for details on how to use functions and what functions are available to create a calculated metric.


#### Generic container

To add a generic container:

* Select ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** from within a container
* Select **[!UICONTROL Container]**. A new empty generic container is added to the **[!UICONTROL Definition]**. You can use a generic container to nest or create a hierarchy in the definition of your calculated metric.


#### Delete a container

To delete a container, select ![Close](/help/assets/icons/Close.svg) at the container level.

>[!MORELIKETHIS]
>
>[Use functions](cm-using-functions.md)
>[Segments](/help/components/segmentation/seg-overview.md)
>
