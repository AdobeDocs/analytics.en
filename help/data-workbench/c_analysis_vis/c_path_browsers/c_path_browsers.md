---
description: A path browser enables you to analyze the sequence in which a particular dimension’s elements were accessed.
seo-description: A path browser enables you to analyze the sequence in which a particular dimension’s elements were accessed.
seo-title: Path browsers
solution: Analytics
title: Path browsers
topic: Data workbench
uuid: 9d62222a-ffcb-4fe1-8bd6-94404744d118
index: y
internal: n
snippet: y
---

# Path browsers

A path browser enables you to analyze the sequence in which a particular dimension’s elements were accessed.

 You create a path browser by dragging and dropping an element of a dimension onto a blank path browser visualization. The element that you drag and drop onto the path browser becomes the root of the path browser. The path browser displays paths that pass through the root, enabling you to see the sequence of elements that were accessed before and after the root.

The following path browser shows the sequence of movies that viewers rated before and after rating the movie *The Aviator*, which is the root of the path browser. Each movie name is an element of the Movie dimension, which is defined in a dataset consisting of movie data that includes movies’ names and viewers’ ratings of those movies.

![](assets/vis_PathBrowser_Movies.png)

You can create path browsers to show the sequence in which elements of any dimension in your dataset were accessed. For example, if you are working with website data, you can create a path browser that shows the sequence of website pages that were accessed before and after the root for each session in which the root was viewed or for each site visitor that viewed the root.

![](assets/vis_PathBrowser_Pages.png)

Every path browser has an associated base dimension, group dimension, level dimension, and metric, which provide keys for interpreting the data shown in the path browser.

* **Base dimension:** When you drag and drop a root element onto the path browser, you are dragging and dropping an element of the base dimension. All of the other elements that appear in the paths are elements of the base dimension. You can change the base dimension by dragging and dropping an element of another dimension onto the path browser. 
* **Level dimension:** Every dimension in your dataset has an associated level dimension (also referred to as a parent). The level dimension for your path browser should be the same as the level dimension (or parent) for your path browser’s base dimension. A path browser’s level dimension is important for two main reasons:

    * As you follow a path from one base dimension element to the next, you move from one level dimension element to the next. For example, suppose that you have created a path browser showing pages of a website. Each page is an element of the Page dimension, and the level dimension for Page is Page View. As you move from one page to the next, you are moving from one page view to the next. 
    * When you select a path of base dimension elements within a path browser, you are selecting data for the corresponding elements of the level dimension. The selection always includes the elements of the level dimension that relate to the root, and it is refined by adding more elements to the path. For example, when you select a path of pages, such as root > A > B, you are selecting data for the page views associated with the root where the next page is A and the next page is B.

      For information about selecting a path in a path browser, see [Selecting Paths](../../c_analysis_vis/c_path_browsers/t_sel_paths.md#task_BF44D08C71954EF2ADEC4B82F840ADEB). For information about selections, see [Making Selections in Visualizations](../../c_vis/c_sel_vis/c_sel_vis.md#concept_012870EC22C7476E9AFBF3B8B2515746).

  >[!NOTE]
  >
  >The path browser ignores the elements of the level dimension with no associated base dimension elements. This situation can occur when you create a path browser from a process map. See [Creating Path Browsers](../../c_analysis_vis/c_path_browsers/c_create_path_browsers.md#concept_E120DE6A740D4B6F98DDA9E2B638F6FF).

* **Group dimension:** The group dimension determines how the elements of the level dimension are grouped to form the paths of a path browser. Specifically, the level dimension elements associated with a single path in a path browser cannot span more than one element of a group dimension.

  To understand this, consider an example using web data. Suppose that the base, level, and group dimensions for your path browser are Page, Page View, and Session, respectively. One path in your path browser shows the page sequence A > B > C. The group dimension (Session) tells you that the page views (elements of the Page View dimension) associated with the page sequence A > B > C occurred during any single session. It is important to note that there might be multiple sessions during which there were page views for the page sequence A > B > C. Therefore, the path showing the page sequence A > B > C represents all of the individual sessions in which the page views for that sequence occurred. 

* **Metric**: The thickness of the path leading to a given element is proportional to the metric’s value for that element. Thicker paths indicate greater metric values than thinner paths.

The label in the top left corner of the path browser names the base and group dimensions represented in the visualization. The name of the level dimension is not visible in the path browser visualization. The label takes the form “Sequence of *base dimension name*+s for each *group dimension name*.” For example, the label Sequence of Movies for each User tells you that the base dimension is Movie and the group dimension is User.

![](assets/vis_PathBrowser_Movies.png)

By right-clicking any element in the path browser, you can see the name of the metric associated with the path browser and its value for that element.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>You can change the default dimensions and metric for a path browser. For instructions to configure a path browser visualization, see [Configuring Path Browsers](../../c_intf_anlys_ftrs/t_config_path_brwsr.md#task_BBB3DDAA140A414F984B697C2B8202A3).

