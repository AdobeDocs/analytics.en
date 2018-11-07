---
description: Visitor clustering lets you leverage customer characteristics to dynamically categorize visitors and generate cluster sets based on selected data inputs, thus identifying groups that have similar interests and behaviors for customer analysis and targeting.
seo-description: Visitor clustering lets you leverage customer characteristics to dynamically categorize visitors and generate cluster sets based on selected data inputs, thus identifying groups that have similar interests and behaviors for customer analysis and targeting.
seo-title: Clusters
solution: Analytics
title: Clusters
topic: Data workbench
uuid: f6fd5510-0587-4339-8678-edff30a9c9f8
index: y
internal: n
snippet: y
---

# Clusters

Visitor clustering lets you leverage customer characteristics to dynamically categorize visitors and generate cluster sets based on selected data inputs, thus identifying groups that have similar interests and behaviors for customer analysis and targeting.

## Clustering Process {#section_9F92B12B4F974F169E82E08C59AE2169}

The clustering process requires you to identify metrics and dimension elements to use as inputs, and allows you to choose a specific target population to apply these elements to create specified clusters. When you run the clustering process, the system uses the metric and dimension inputs to determine appropriate initial centers for the specified number of clusters. These centers are then used as a starting point to apply the K-Means algorithm. 

![](assets/K_algorithm.png)

|  The initial centers are intelligently chosen via a Canopy Clustering pass.  | Data clusters are created by associating every data point to the nearest center.  | The mean of each of the K clusters becomes the new center.  | The algorithm is repeated in steps 2 and 3 until convergence is reached. This can take multiples passes.  |
|---|---|---|---|

The **[!UICONTROL Maximum iterations]** in the **[!UICONTROL Options]** menu allows the analyst to specify the maximum number of iterations to be performed by the clustering algorithm. Setting this option may result in faster completion of the clustering process based on the maximum iterations cap at the expense of exact convergence of the cluster centers.

>[!NOTE]
>
>Once the clusters have been defined, the Cluster Dimension can be saved for use just like any other dimension. It can also be loaded into the Cluster Explorer to examine the separation of cluster centers.

## KMeans algorithms {#section_DD4A29C1F64B4BB8A3A5322E642441B3}

In the [Cluster Builder](https://marketing.adobe.com/resources/help/en_US/insight/client/?f=c_visitor_cluster), you can now select **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** to select algorithms when defining clusters.

* **[!UICONTROL KMeans]**. This algorithm uses canopy clustering to define the centers of the cluster. 
* **[!UICONTROL KMeans++]**. This algorithm expedites cluster building when running against large sets of data.

<a id="section_8193A6D60C5540BB985085BE670B4544"></a>

KMeans++ is an improved implementation of KMeans clustering algorithm because it provides better initialization of initial k centers. (The original KMeans algorithm chooses initial centers randomly.) KMeans++ selects the first center randomly. The remaining k-1 centers will be chosen one by one based on the distance a data point is to the closest existing center. The furthest data points have a better chance to be chosen as a new center than nearby data points. After the initial center is chosen, the procedure is performed exactly the same as the original KMeans clustering.

The workflow for KMeans++ is exactly the same as the workflow for KMeans clustering, except that you need to select **Options** > **Algorithm** > **KMeans++** in the cluster builder.

>[!NOTE]
>
>Each DPU runs its own KMeans++ procedure on its own data portion. If the DPU has enough available memory (the ratio is configurable in the PAServer.cfg file), then the data of those involved variables will be brought into memory. The remaining k-1 initial center selection and converging iterations all happen in memory, which is faster than the previous KMeans clustering.

