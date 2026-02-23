---
description: Understand how an inter-dimensional flow lets you examine user paths across various dimensions.
title: Inter-Dimensional Flows
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
---
# Inter-dimensional flows

An inter-dimensional flow lets you examine user paths across various dimensions. 

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Inter-dimensional flows](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

This article shows how to use this flow for two use cases: mobile app interactions and events, and how campaigns drive web visits.

## Mobile app interactions and events

The [!UICONTROL Screen Name] dimension is used in this example flow to see how users use the various screens (scenes) in the app. The top screen returned is **[!UICONTROL luma: content: ios: en: home]**, which is the home page of the app:

![A flow showing the Item Added.](assets/flowapp.png)

To explore the interaction between screens and event types (like add to cart, purchases, and others) in this app, drag and drop the **[!UICONTROL Event Types]** dimension:

* On top of any available step in the flow, to replace that dimension:

  ![A flow showing the Page dimension dragged dragged to the multiple areas.](assets/flowapp-replace.png)

* Outside of the current flow visualization, to add the dimension:

  ![A flow showing the Page dimension dragged to the white space at the end.](assets/flowapp-add.png)

The flow visualization below shows the result of adding the **[!UICONTROL Event Types]** dimension. The visualization provides insights to how mobile app users move through various screens in the app before adding products to a cart, close the application, are presented an offer, and more.

![A fLow showing the Page dimension results at the top of the list.](assets/flowapp-result.png)

## How campaigns drive web visits

You want to analyze which campaigns drive visits to the web site. You create a flow visualization with the **[!UICONTROL Campaign Name]** as the dimension

![Flow web campaign name dimension](assets/flowweb.png)

You replace the last **[!UICONTROL Campaign Name]** dimension with the **[!UICONTROL Formatted Page Name]** dimension and add another **[!UICONTROL Formatted Page Name]** dimension at the end of the flow visualization.

![Flow web campaign name and web page dimension](assets/flowweb-replace.png)

You can hover over any of the flows to see more details. For example which campaigns have resulted in a Cart checkout.

![Flow web campaign name and web page dimension hover](assets/flowweb-hover.png)
