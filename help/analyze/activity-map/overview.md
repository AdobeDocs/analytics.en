---
description: Rank link activity using visual overlays to monitor audience engagement of your web pages.
title: Activity Map overview
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
---
# Activity Map overview

Adobe Analytics Activity Map is a feature within Adobe Analytics that provides a visual representation of user engagement on web pages and mobile apps. It enables marketers and analysts to track and analyze user interactions such as clicks and scrolling behavior. Activity Map generates heat maps and overlay reports that show the most popular elements on a webpage, helping you optimize your digital experiences.

This section of the documentation focuses on the Activity Map overlay. However, there are other important parts to using Activity Map:

* **Report suite setting**: A report suite must have Activity Map enabled. See [Activity Map Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) in Report suite settings.
* **Implementation**: Most Activity Map reporting is available out-of-the-box. However, some websites might require additional implementation to get the most out of link tracking. The following implementation variables are available:
  * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filter click data by link name.
  * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filter click data by region name.
  * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): Change the attribute that populates the Activity Map Region dimension.
  * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): Customize the logic that Activity Map uses to populate the Activity Map Link dimension.
  * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): Customize the logic that Activity Map uses to populate the Activity Map Region dimension.
* **Dimensions**: In addition to the overlay extension, Activity Map provides several dimensions that you can use in Analysis Workspace.
  * [Activity Map Link](/help/components/dimensions/activity-map-link.md): The link name that was clicked.
  * [Activity Map Region](/help/components/dimensions/activity-map-region.md): The region name that was clicked.
  * [Activity Map Page](/help/components/dimensions/activity-map-page.md): The page name at the time that the link was clicked.
  * [Activity Map Link By Region](/help/components/dimensions/activity-map-link-by-region.md): A concatenated value of Activity Map Link and Activity Map Region.

## Features and benefits

* **Visualization of user engagement**: Activity Map offers a dynamic visual representation of user behavior, enabling you to see exactly where users click. This visual data makes it easier to identify patterns, trends, and areas of interest. You can then make informed decisions about design, content placement, and user flow.

* **Heat maps**: Activity Map generates heat maps that display the most clicked or interacted areas of a webpage. Heat maps use color-coding to represent the level of engagement, allowing you to identify hotspots and prioritize attention to high-impact areas. This information can be valuable for optimizing call-to-action buttons, links, forms, or any other interactive elements.

* **Overlay reports**: Overlay reports in Activity Map provide detailed click metrics for specific elements on a webpage. By understanding the click-through rates and engagement levels of individual elements, you can fine-tune your design and content strategies to enhance user experiences.

* **Segment analysis**: You can analyze user behavior based on different segments, such as traffic sources, demographics, or personas. By segmenting the data, you can uncover valuable insights into specific user groups, enabling personalized experiences and targeted marketing strategies.

## Practical applications

* **Website optimization**: Activity Map helps you optimize your websites by identifying underperforming elements, improving navigation, and enhancing the overall user experience. By analyzing user interactions, you can make data-driven decisions to streamline user flows, simplify forms, or adjust content placement for maximum impact.

* **Conversion rate optimization**: By visualizing user engagement and analyzing click-through rates, Activity Map plays a crucial role in CRO efforts. You can identify barriers to conversion and experiment with different design variations to optimize conversion funnels, landing pages, and checkout processes.

* **A/B testing**: Activity Map can be combined with A/B testing to measure the impact of design or content changes. By comparing engagement metrics between different versions of a webpage, you can determine which variations lead to higher user engagement, conversion rates, or revenue.

