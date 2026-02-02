# Snippets

## Legacy Report Builder {#legacy-arb}

>[!IMPORTANT]
>
>A new and streamlined [Report Builder](/help/analyze/report-builder/rb-overview.md) is available since October 16, 2024. This Report Builder is supported on macOS, Windows, and web browsers and can be used with Adobe Analytics and Customer Journey Analytics.
>This Legacy Report Builder add-in version still works. You can [convert your legacy workbooks](/help/analyze/report-builder/convert-workbooks.md) to the new Report Builder.

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

## Attribution container {#attribution-container}

An attribution container defines the desired scope for the attribution. Possible options are: 

* **Visit**: Looks at conversions from the scope of the visit container. When **[!UICONTROL Visit]** is selected, the [Attribution lookback window](#atribution-lookback-window) is automatically set to **[!UICONTROL Reporting window]** and cannot be changed.
* **Visitor**: Looks at conversions from the scope of the visitor container.

## Atribution lookback window {#attribution-lookback-window}

A lookback window is the amount of time a conversion should look back to include touch points. If a dimension item is set outside of the lookback window, the value is not included in any attribution calculations.

* **[!UICONTROL Reporting window]**: Looks back up to the start of the reporting window from when the conversion happened.
* **14 Days**: Looks back up to 14 days from when the conversion happened.
* **30 Days**: Looks back up to 30 days from when the conversion happened.
* **60 Days**: Looks back up to 60 days from when the conversion happened.
* **90 Days**: Looks back up to 90 days from when the conversion happened.
* **Custom Time:** Allows you to set a custom lookback window from when a conversion happened. You can specify the number of minutes, hours, days, weeks, months, or quarters. For example, if a conversion happened on February 20, a lookback window of five days would evaluate all dimension touchpoints from February 15 to February 20 in the attribution model.

## Attribution example {#attribution-example}

Consider the following example:

1. On September 15, a visitor arrives to your site through a paid search advertisement, then leaves.
1. On September 18, the visitor arrives to your site again through a social media link they got from a friend. They add several items to their cart, but do not purchase anything.
1. On September 24, your marketing team sends them an email with a coupon for some of the items in their cart. They apply the coupon, but visit several other sites to see if any other coupons are available. They find another through a display ad, then ultimately make a purchase for $50.

Depending on your attribution model, container and channels receive different credit. See table below for examples:

| Model | Container | Lookback window | Explanation |
|---|---|---|---|
| First touch | Visit | Reporting window | Attribution looks at only the third visit. Between email and display, email was first, so email gets 100% credit for the $50 purchase. |
| First touch | Visitor | 30 Days | Attribution looks at all three visits. Paid search was first, so it gets 100% credit for the $50 purchase. |
| Linear | Visit | Reporting window | Credit is divided between email and display. Both of these channels each get $25 credit. |
| Linear | Visitor | 30 Days | Credit is divided between paid search, social, email, and display. Each channel gets $12.50 credit for this purchase. |
| J-shaped | Visitor | 30 Days | Credit is divided between paid search, social, email, and display.<ul><li>60% credit is given to display, for $30.</li><li>20% credit is given to paid search, for $10.</li><li>The remaining 20% is divided between social and email, giving $5 to each.</li></ul> |
| Time Decay | Visitor | 30 Days | <ul><li>Gap of zero days between display touch point and conversion. `2^(-0/7) = 1`</li><li>Gap of zero days between email touch point and conversion. `2^(-0/7) = 1`</li><li>Gap of six days between social touch point and conversion. `2^(-6/7) = 0.552`</li><li>Gap of nine days between paid search touch point and conversion. `2^(-9/7) = 0.41`</li>Normalizing these values results in the following:<ul><li>Display: 33.8%, getting $16.88</li><li>Email: 33.8% getting $16.88</li><li>Social: 18.6%, getting $9.32</li><li>Paid Search: 13.8%, getting $6.92</li></ul></li></ul> |

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



## Tag filter section {#tagfiltersection}

| Tags   | Description |
|---|---|
| ![Tags](/help/assets/filter-tag.png){width="300"} | The **[!UICONTROL Tags]** section lets you filter on tags. <ul><li>You can ![Search](/help/assets/icons/Search.svg) *Search Tags* to search for tags you can use to filter.</li><li>You can select more than one tag. The tags available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(1)**: The number of selected tags (if one or more tags are selected).</li><li>**2︎⃣**: The number of tags available for the items resulting from the current filter.</li><li>7︎⃣: The number of items associated with the specific tag.</li></ul></li></ul> |


## Report suite filter section {#reportsuitefiltersection}

| Report  suite | Description |
|---|---|
| ![Repost suite](/help/assets/filter-reportsuite.png){width="300"} | The **[!UICONTROL Report suite]** section lets you filter on report uites. <ul><li>You can ![Search](/help/assets/icons/Search.svg) *Search Report suites* to search for report suites you can use to filter.</li><li>You can select more than one report suite. The report suites available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(2)**: The number of selected report suites (if one or more report suites are selected).</li><li>**3︎⃣**: The number of report suites available for the items resulting from the current filter.</li><li>4︎⃣: The number of items associated with the specific report suite.</li></ul></li></ul> |

## Enabled status filter section {#enabledstatusfiltersection}

| Enabled status | Description |
|---|---|
| ![Enabled status](/help/assets/filter-enabledstatus.png){width="300"} | The **[!UICONTROL Enabled status]** section lets you filter on enabled status. <ul><li>You can select more than one status.</li><li>The numbers indicate:<ul><li>**(2)**: The number of selected statuses (if one or more statuses are selected).</li><li>**2︎⃣**: The number of statuses available for the items resulting from the current filter.</li><li>1︎⃣: The number of items associated with the specific status.</li></ul></li></ul> |

## Type filter section {#typefiltersection}

| Type | Description |
|---|---|
| ![Type](/help/assets/filter-type.png){width="300"} | The **[!UICONTROL Type]** section lets you filter on type. <ul><li>You can select more than one type.</li><li>The numbers indicate:<ul><li>**(2)**: The number of selected types (if one or more types are selected).</li><li>**1︎⃣**: The number of types available for the items resulting from the current filter.</li><li>3︎⃣: The number of items associated with the specific type.</li></ul></li></ul> |

## Owner filter section {#ownerfiltersection}

| Owner | Description |
|---|---|
| ![Owners](/help/assets/filter-owners.png){width="300"} | The **[!UICONTROL Owner]** section lets you filter on owners. <ul><li>You can ![Search](/help/assets/icons/Search.svg) *Search Owners* to search for owners you can use to filter.</li><li>You can select more than one owner. The owners available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(2)**: The number of selected owners (if one or more owners are selected).</li><li>**3︎⃣**: The number of owners available for the items resulting from the current filter.</li><li>4︎⃣: The number of items associated with the specific owner.</li></ul></li></ul> |

## Other filters filter section {#otherfiltersfiltersection} 

| Other filters | Description |
|---|---|
| ![Other filters](/help/assets/filter-other.png){width="300"} | The **[!UICONTROL Other filters]** section lets you filter on other predefined filter.<ul><li>You can select one or more of the following options:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> What you can select depends on your role and permissions.</li><li>You can select more than one other filter. The other filters available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(1)**: The number of selected other filters (if one or more other filters are selected).</li><li>**5︎⃣**: The number of other filters available for the items resulting from the current filter.</li><li>4︎⃣: The number of items associated with the specific other filter.</li></ul></li></ul> |

## Date range filter section  {#daterangefiltersection} 

| Applied date range | Description |
|---|---|
| ![Date range](/help/assets/filter-daterange.png){width="300"} | The Applied date range section let you filter on a date range applicable to the items.<ol><li>Select a date range.</li><li>In the calendar popup define a date range, or select one of the available presets.<br>Alternatively, you can also specify a date range directly in the Date range section of the Filter panel.</li></ol><ul><li>The numbers indicate:<ul><li>**(1)**: The number of modified date ranges modified from default presets.</li><li>**5︎⃣**: The number of date ranges available for the items resulting from the current filter.</li></ul> |


## Classification importer deprecation {#classification-importer-deprecation}

>[!WARNING]
>
>Classification importer will be deprecated on **August 31, 2026**. Please switch to use the [Classification sets](/help/components/classifications/sets/overview.md) experience to ensure continued functionality.
>



## Classification Rule Builder deprecation {#classification-rulebuilder-deprecation}

>[!WARNING]
>
>Classification rule builder will be deprecated on **August 31, 2026**. Please switch to use the [Classification sets rules](/help/components/classifications/sets/manage/rules.md) experience, once available, to ensure continued functionality.
>

