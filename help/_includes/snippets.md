# Snippets

## Legacy Report Builder {#legacy-arb}

>[!IMPORTANT]
>
>A new and streamlined [Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview) was released on October 16, 2024. It is supported on Mac, Windows, and web browsers.
>This Legacy Report Builder add-in version still works. You can [convert your legacy workbooks](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks) to the new Report Builder.

## Reports & Analytics end-of-life announcement {#ra-eol}

>[!IMPORTANT]
>
>Effective **January 17, 2024**, Adobe discontinued Reports & Analytics and its accompanying reports and features. At that time, Reports & Analytics and all of its reports and schedules stopped working. The reports, visualizations and underlying technology that power Reports & Analytics no longer meet Adobe's technology standards. Most Reports & Analytics features are available within Analysis Workspace. For information, see [Use templates](/help/analyze/analysis-workspace/templates/use-templates.md).
> 
>Since the release of Analysis Workspace in 2015, Reports & Analytics functionality and capabilities have been moved to Analysis Workspace and a threshold of workflow parity has been reached. This notice explains the end-of-life process.
>
>Read more about the Reports & Analytics [End-of-life announcement](https://www.adobe.com/go/analytics_rnaeol_en).

## Components sort options {#components-sort-options}

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Recommended**] | Sorts components with those that are recommended at the top of the list. Components that are used most frequently and most recently by you or by others in your organization are shown higher in the list. |
   | [!UICONTROL **Alphabetical**] | Sorts components alphabetically. |
   | [!UICONTROL **Categorical**] | Sorts components according to component type (dimension, metric, segment, date range). |

   {style="table-layout:auto"}

## Release phase Limited Testing {#release-limited-testing}

>[!AVAILABILITY]
>
>The functionality described in this article is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Analytics release process, see [Adobe Analytics feature releases](/help/release-notes/releases.md).

## Release phase Limited Testing section {#release-limited-testing-section}

>[!AVAILABILITY]
>
>The functionality described in this section is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Analytics release process, see [Adobe Analytics feature releases](/help/release-notes/releases.md).


## Plug-in disclaimer {#plug-in}

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Adobe Account Team. They can arrange a meeting with a consultant for assistance.


## Only available to existing customers {#available-existing-customers}

>[!AVAILABILITY]
>
>The functionality described in this section is only available to existing customers that already have a license for the functionality. The functionality is no longer offered as an additional add-on to existing or new customers. 
>



## Attribution models {#attribution-models-details}

An attribution model determines which dimension items get credit for a metric when multiple values are seen within a metric's lookback window. Attribution models only apply when there are multiple dimension items set within the lookback window. If only a single dimension item is set, that dimension item gets 100% credit regardless of attribution model used.

| Icon | Attribution model | Definition |
| :---: | :--- | --- |
| ![Last Touch](/help/assets/icons/AttributeLastTouch.svg) | Last Touch | Gives 100% credit to the touch point occurring most recently before conversion. This attribution model is typically the default value for any metric where an attribution model is not otherwise specified. Organizations typically use this model where the time to conversion is relatively short, such as with analyzing internal search keywords. |
| ![First Touch](/help/assets/icons/AttributeFirstTouch.svg) | First Touch | Gives 100% credit to the touch point first seen within the attribution lookback window. Organizations typically use this model to understand brand awareness or customer acquisition. |
| ![Linear](/help/assets/icons/AttributeLinear.svg) | Linear | Gives equal credit to every touch point seen leading up to a conversion. It is useful where conversion cycles are longer or require more frequent customer engagement. Organizations typically use this attribution model measuring mobile app notification effectiveness or with subscription-based products. |
| ![Participation](/help/assets/icons/AttributeParticipation.svg) | Participation | Gives 100% credit to all unique touch points. Since every touch point receives 100% credit, metric data typically adds up to more than 100%. If a dimension item appears multiple separate times leading up to a conversion, values are deduplicated to 100%. This attribution model is ideal in situations where you want to understand which touch points customers are exposed to the most. Media organizations typically use this model to calculate content velocity. Retail organizations typically use this model to understand which parts of their site are critical to conversion. |
| ![Same Touch](/help/assets/icons/AttributeSameTouch.svg) | Same Touch | Gives 100% credit to the same event where the conversion occurred. If a touch point does not happen on the same event as a conversion, It is bucketed under "None". This attribution model is sometimes equated to having no attribution model at all. It is valuable in scenarios where you do not want values from other events affecting how a metric gives credit to dimension items. Product or design teams can use this model to assess the effectiveness of a page where conversion happens. |
| ![U Shaped](/help/assets/icons/AttributeUShaped.svg) | U Shaped | Gives 40% credit to the first interaction, 40% credit to the last interaction, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 50% credit is given to both. This attribution model is best used in scenarios where you value the first and last interactions the most, but don't want to entirely dismiss additional interactions in between. |
| ![J Curve](/help/assets/icons/AttributeJCurve.svg) | J Curve | Gives 60% credit to the last interaction, 20% credit to the first interaction, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 75% credit is given to the last interaction, and 25% credit is given to the first. Similar to U-Shaped, this attribution model favors the first and last interactions, but more heavily favors the last interaction. |
| ![Inverse J](/help/assets/icons/AttributeInverseJ.svg) | Inverse J | Gives 60% credit to the first touch point, 20% credit to the last touch point, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 75% credit is given to the first interaction, and 25% credit is given to the last. Similar to J-Shaped, this attribution model favors the first and last interactions, but more heavily favors the first interaction. |
| ![Time Decay](/help/assets/icons/AttributeTimeDecay.svg) | Time Decay | Follows an exponential decay with a custom half-life parameter, where the default is 7 days. The weight of each channel depends on the amount of time that passed between the touch point initiation and the eventual conversion. The formula used to determine credit is `2^(-t/halflife)`, where `t` is the amount of time between a touch point and a conversion. All touch points are then normalized to 100%. Ideal for scenarios where you want to measure attribution against a specific and significant event. The longer a conversion happens after this event, the less credit is given. |
| ![Custom](/help/assets/icons/AttributeCustom.svg) | Custom | Allows you to specify the weights that you want to give to first touch point, last touch point, and any touch points in between. Values specified are normalized to 100% even if the custom numbers entered do not add to 100. For conversions with a single touch point, 100% credit is given. For interactions with two touch points, the middle parameter is ignored. The first and last touch points are then normalized to 100%, and credit is assigned accordingly. This model is ideal for analysts who want full control over their attribution model and have specific needs that other attribution models do not fulfill. |
| ![Algorithmic](/help/assets/icons/AttributeAlgorithmic.svg) | Algorithmic | Uses statistical techniques to dynamically determine the optimal allocation of credit for the selected metric. The algorithm used for attribution is based on the Harsanyi Dividend from cooperative game theory. The Harsanyi dividend is a generalization of the Shapley value solution (named after Lloyd Shapley, a Nobel Laureate economist) to distributing credit among players in a game with unequal contributions to the outcome.<br>At a high level, attribution is calculated as a coalition of players to which a surplus must be equitably distributed. Each coalition's surplus distribution is determined according to the surplus that was previously created by each subcoalition (or previously participating dimension items) recursively. For more details, see John Harsanyi's and Lloyd Shapley's original papers:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Atribution lookback window {#attribution-lookback-window}

A lookback window is the amount of time a conversion should look back to include touch points. If a dimension item is set outside of the lookback window, the value is not included in any attribution calculations.

* **14 Days**: Looks back up to 14 days from when the conversion happened.
* **30 Days**: Looks back up to 30 days from when the conversion happened.
* **60 Days**: Looks back up to 60 days from when the conversion happened.
* **90 Days**: Looks back up to 90 days from when the conversion happened.
* **Visit**: Looks back up to the beginning of the visit where a conversion happened.
* **Visitor (Reporting Window)**: Looks at all visits back up to the first of the month of the current date range. For example, if the report date range is September 15 - September 30, the visitor lookback date range includes September 1 - September 30. If you use this lookback window, you can occasionally see that dimension items are attributed to dates outside of your reporting window.
* **Custom Time:** Allows you to set a custom lookback window from when a conversion happened. You can specify the number of minutes, hours, days, weeks, months, or quarters. For example, if a conversion happened on February 20, a lookback window of five days would evaluate all dimension touchpoints from February 15 to February 20 in the attribution model.

## Attribution example {#attribution-example}

Consider the following example:

1. On September 15, a person arrives to your site through a paid search advertisement, then leaves.
1. On September 18, the person arrives to your site again through a social media link they got from a friend. They add several items to their cart, but do not purchase anything.
1. On September 24, your marketing team sends them an email with a coupon for some of the items in their cart. They apply the coupon, but visit several other sites to see if any other coupons are available. They find another through a display ad, then ultimately make a purchase for $50.

Depending on your lookback window and attribution model, channels receive different credit. The following are some examples:

* Using **first touch** and a **session lookback window**, attribution looks at only the third visit. Between email and display, email was first, so email gets 100% credit for the $50 purchase.

* Using **first touch** and a **person lookback window**, attribution looks at all three visits. Paid search was first, so it gets 100% credit for the $50 purchase.

* Using **linear** and a **session lookback window**, credit is divided between email and display. Both of these channels each get $25 credit.
Using **linear** and a **person lookback window**, credit is divided between paid search, social, email, and display. Each channel gets $12.50 credit for this purchase.

* Using **J-shaped** and a **person lookback window**, credit is divided between paid search, social, email, and display.

  * 60% credit is given to display, for $30.
  * 20% credit is given to paid search, for $10.
  * The remaining 20% is divided between social and email, giving $5 to each.

* Using **Time Decay** and a **person lookback window**, credit is divided between paid search, social, email, and display. Using the default 7-day half-life:

  * Gap of zero days between display touch point and conversion. `2^(-0/7) = 1`
  * Gap of zero days between email touch point and conversion. `2^(-0/7) = 1`
  * Gap of six days between social touch point and conversion. `2^(-6/7) = 0.552`
  * Gap of nine days between paid search touch point and conversion. `2^(-9/7) = 0.41`
  * Normalizing these values results in the following:
  
      * Display: 33.8%, getting $16.88
      * Email: 33.8% getting $16.88
      * Social: 18.6%, getting $9.32
      * Paid Search: 13.8%, getting $6.92

Conversion events that typically have whole numbers are divided if credit belongs to more than one channel. For example, if two channels contribute to an order using a Linear attribution model, both channels get 0.5 of that order. These partial metrics are summed across all people then rounded to the nearest integer for reporting.

## Journey visualization comparisons {#journey-visualization-comparisons}

Various visualizations in Customer Journey analytics are designed to analyze the journeys you provide to your customers.

Use the following information to choose the visualization that best meets your needs.

| Function | Journey canvas | Fallout | Flow |
|---------|----------|---------|---------|
| **Predefined sequence of pages** | Yes</br>Combines predefined and exploratory analysis. The eventual path is used when using predefined nodes on the path (visitors are counted as long as they eventually move from one predefined node to the other). The immediate (not eventual) next nodes can also be shown.  | Yes</br>The path can be an eventual path or can be constrained to the next touchpoint | No |
| **Exploratory sequence of pages (ad hoc analysis)** | Yes</br>Combines predefined and exploratory analysis. The eventual path is used when using predefined nodes on the path (visitors are counted as long as they eventually move from one predefined node to the other). The immediate (not eventual) next nodes can also be shown. | Limited</br>Allows you to right-click and view immediate fallout in a Freeform table. | Yes</br>Exploratory analysis only. Always within one dimension instance between nodes. This means that each node shows the immediate (not eventual) next touchpoint along the path. |
| **Shows where people left (fell out) and continued through (fell through)** | Yes</br>Shows for both predefined and exploratory journeys  | Yes</br>Shows predefined journeys  | Yes</br>Shows for exploratory journeys  |
| **Linear journeys** | Yes | Yes | No |
| **Non-linear journeys with multiple entry points and paths** | Yes | No | Yes |
| **Primary metric** | Any metric, including calculated metrics | Only Session or Person | Only Occurrences (Path views) |
| **Secondary metric** | Yes<p>Any metric, including calculated metrics</p> | No | No  |
| **Component support in nodes or touchpoints** | Metrics, dimension items, filters, and date ranges.| Metrics, dimension items, filters, and date ranges. | Only dimension items (except for the starting and ending touchpoint)  |
| **Compare filters** | No | Yes<p>Perform side-by-side comparisons of two different filters in the same report.</p> | No |
| **Drag-and-drop component interaction** | Yes | Yes | No |
| **Adobe Journey Optimizer journeys** | Yes</br>Open journeys from Journey Optimizer for deeper analysis and customization | No |  No |

{style="table-layout:auto"}
