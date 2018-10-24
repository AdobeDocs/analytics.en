---
description: Information about the different types of process maps.
seo-description: Information about the different types of process maps.
seo-title: Types of process maps
solution: Analytics
title: Types of process maps
topic: Data workbench
uuid: bde236f7-9380-422f-a2c0-d18c181d9ebe
index: y
internal: n
snippet: y
---

# Types of process maps

Information about the different types of process maps.

## 2D process maps {#section_EA7FBDB80B1B44AEBCD9E4090B6540BF}

Two-dimensional process maps provide a two-dimensional view of the activity between dimension elements. The size of a node in a 2D process map is proportional to the value of the metric associated with that node. In addition, both the thickness and intensity of an arrow between two nodes are proportional to the average of the metric’s values for those nodes.

Within a 2D process map, you can do any of the following tasks:

* Select, move, remove, and label nodes 
* Make selections 
* Save dimensions 
* Create other visualizations 
* Activate color links 
* Display metric quantities 
* Add callouts

The 2D process map in the following example shows nodes corresponding to the names of movies. Each movie name is an element of the Movie dimension, which is defined in a dataset consisting of movie data. The Movie dimension is the base dimension for this process map.

![](assets/vis_2DProcessMap_MovieNodes.png)

In the example, the size of each node and the thickness and intensity of each arrow are proportional to the Ratings metric, which is a count of ratings that a movie received. Therefore, a movie with a large node, such as *Independence Day*, has more ratings than a movie with a small node, such as *Event Horizon*. You also can see that more movie viewers rated *Independence Day* before *Cold Mountain* than rated the same movies in the opposite order. Note that the arrows do not indicate that viewers rated *Independence Day* and then rated *Cold Mountain* immediately afterward, or vice versa. Viewers might have rated other movies in between, but these movies are not shown on this map.

## 2D metric maps {#section_A9B846FC71224058918FBC378315EFFE}

Two-dimensional metric maps are a type of 2D process map that position nodes based on the value of a particular metric. In many cases, the metric used with the 2D metric map is either Conversion or Retention. Conversion and retention maps help you understand what steps in the processes of your customer-facing channels influence customer conversion and retention.

>[!NOTE]
>
>The metric that you use with a 2D metric map must be expressed as a percentage.

In a conversion metric map, nodes with 0 percent conversion are plotted at the left of the graph, and pages with 100 percent conversion are plotted at the right. Activity between nodes is displayed, making it easy to see which steps in a process lead to increased or decreased conversion and which steps drive abandonment. A process-conversion analysis is an effective way to compare processes or compare different implementations of the same process.

![](assets/vis_2DMetricMap_Conversion.png)

Similarly, retention maps show elements with 0 percent retention at the left of the graph and elements with 100 percent retention at the right. You can see the retention rate for each node on the map, which helps you determine which elements influence customers to return.

![](assets/vis_2DMetricMap_Retention.png)

>[!NOTE]
>
>You cannot move nodes on 2D metric maps horizontally. Metric maps are designed to position nodes left to right based on their metric values.

## 3D process maps {#section_80ACB63EA0994AF1AF7FAEF3C6264E51}

Three-dimensional process maps provide a three-dimensional view of the activity between dimension elements. The height of a bar in a 3D process map is proportional to the value of the metric associated with that node. As with 2D process maps, both the thickness and intensity of the connectors between two nodes are proportional to the average of the metric’s values for those nodes. Within a 3D process map, you can do any of the following tasks:

* Select, move, remove, and label nodes 
* Make selections 
* Save dimensions 
* Create other visualizations 
* Activate color links

The 3D process map in the following example shows nodes corresponding to the pages of a website. Each page is an element of the Page dimension, which is defined in a dataset consisting of web traffic data. The Page dimension is the base dimension for this process map.

![](assets/vis_3DProcessMap_PageNodes.png)

In the example, the height of each bar and the thickness and intensity of each connector are proportional to the Sessions metric, a count of sessions in which the pages were viewed. Therefore, a page with tall bar, such as /faq/all/FAQs, was viewed during more sessions than a page with a short bar, such as /vs/demo. Note that the connections between two pages do not indicate that one page was viewed immediately before or after another during a given session. Other pages might have been viewed during the same session, but these pages are not shown on this map. 
