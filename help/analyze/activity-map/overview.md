---
description: Rank link activity using visual overlays to monitor audience engagement of your web pages.
title: Activity Map overview
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
TQID: https://experienceleague.adobe.com/1-o8wAr6cY8jSR2facQEvh--wvXByJf6R01r4RcVEhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Activity Map overview

Adobe Analytics Activity Map is a feature within Adobe Analytics that provides a visual representation of user engagement on web pages and mobile apps. It enables marketers and analysts to track and analyze user interactions such as clicks and scrolling behavior. Activity Map generates heat maps and overlay reports that show the most popular elements on a webpage, helping you optimize your digital experiences.

Activity Map as a concept is made of several important components:

* **Report suite setting**: A report suite must have Activity Map enabled before you can start using it. See [Activity Map Reporting](/help/admin/tools/manage-rs/edit-settings/activity-map.md) in Report suite settings.
* **Implementation**: Most Activity Map reporting is available out-of-the-box. However, some websites might require additional implementation to get the most out of link tracking. The following implementation variables are available:
  * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filter click data by link name.
  * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filter click data by region name.
  * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): Change the attribute that populates the Activity Map Region dimension.
  * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): Customize the logic that Activity Map uses to populate the Activity Map Link dimension.
  * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): Customize the logic that Activity Map uses to populate the Activity Map Region dimension.
* **Overlay**: A browser extension that allows you to see click data overlaid on your website. See [Activity Map extension interface](overlay/overview.md) for more information. This feature is not available for Web SDK implementations.
* **Dimensions**: In addition to the overlay extension, Activity Map provides several dimensions that you can use in Analysis Workspace.
  * [Activity Map Link](/help/components/dimensions/activity-map-link.md): The link name that was clicked.
  * [Activity Map Region](/help/components/dimensions/activity-map-region.md): The region name that was clicked.
  * [Activity Map Page](/help/components/dimensions/activity-map-page.md): The page name at the time that the link was clicked.
  * [Activity Map Link By Region](/help/components/dimensions/activity-map-link-by-region.md): A concatenated value of Activity Map Link and Activity Map Region.

## Features and benefits

* **Visualization of user engagement**: Activity Map offers a dynamic visual representation of user behavior, enabling you to see exactly where users click. This visual data makes it easier to identify patterns, trends, and areas of interest. You can then make informed decisions about design, content placement, and user flow.

* **Heat maps**: Activity Map generates heat maps that display the most clicked or interacted areas of a webpage. Heat maps use color-coding to represent the level of engagement, allowing you to identify hotspots and prioritize attention to high-impact areas. This information can be valuable for optimizing call-to-action buttons, links, forms, or any other interactive elements.

* **Overlay reports**: Overlay reports in Activity Map provide detailed click metrics for specific elements on a webpage. By understanding the click-through rates and engagement levels of individual elements, you can fine-tune your design and content strategies to enhance user experiences. This feature is not available for Web SDK implementations.

* **Segment analysis**: You can analyze user behavior based on different segments, such as traffic sources, demographics, or personas. By segmenting the data, you can uncover valuable insights into specific user groups, enabling personalized experiences and targeted marketing strategies.

## Practical applications

* **Website optimization**: Activity Map helps you optimize your websites by identifying underperforming elements, improving navigation, and enhancing the overall user experience. By analyzing user interactions, you can make data-driven decisions to streamline user flows, simplify forms, or adjust content placement for maximum impact.

* **Conversion rate optimization**: By visualizing user engagement and analyzing click-through rates, Activity Map plays a crucial role in CRO efforts. You can identify barriers to conversion and experiment with different design variations to optimize conversion funnels, landing pages, and checkout processes.

* **A/B testing**: Activity Map can be combined with A/B testing to measure the impact of design or content changes. By comparing engagement metrics between different versions of a webpage, you can determine which variations lead to higher user engagement, conversion rates, or revenue.

