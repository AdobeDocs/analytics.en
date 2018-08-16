---
description: null
seo-description: null
seo-title: Optimizing performance
title: Optimizing performance
uuid: 6be15528-382e-44c7-b11f-64e08072ca97
index: y
internal: n
snippet: y
translate: y
---

# Optimizing performance


## Best practices for optimizing Analysis Workspace performance factors {#section_24952C84A7CA4F19A5671E8E1729AB64}

Certain factors can influence the performance of a project within Analysis Workspace. It’s important to know what those contributors are before you start building a project so that you can plan &amp;amp; build the project in the most optimal way. Below is a list of factors that will impact performance &amp;amp; best practices for optimizing your projects. Analysis Workspace performance is one of Adobe’s top priorities and something we are continuing to improve each day. 

<table id="table_E9EFB7BF73CD41CD9F6975C7FD14B7C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Performance Factor </th> 
   <th colname="col2" class="entry"> Best Practice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Range of data requested</b> </p> <p>The range of data requested throughout a project will influence Analysis Workspace performance. </p> </td> 
   <td colname="col2"> <p>Where possible, don’t pull in more data than you need. </p> <p>Remember that date ranges (purple components) override the panel date range. As a result, if you are using different date ranges as columns (e.g. last month, last week and yesterday columns), the panel date range does not have to span all of the column date ranges. It can simply be set to yesterday, because the data ranges used in the freeform table will override the panel. For more information on working with date ranges in Analysis Workspace, watch <a href="https://www.youtube.com/watch?v=ybmv6EBmhn0" format="https" scope="external"> this video </a>. </p> <p>Use <a href="../../analysis_workspace_bucket/analysis-workspace-components/calendar/time_comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> date comparison options </a> to pull in the specific time periods of data you want to compare. For example, if you need to show last month's data compared to same month last year, rather than setting the panel to the last 13 months of data, simply use the compare time periods option to show year-over-year performance. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Number of visualizations </b> </p> <p>The number of graph visualizations contained in one project will affect overall responsiveness of Analysis Workspace. Each time a graph visualization is added, you will typically make a <a href="../../analysis_workspace_bucket/freeform-analysis-visualizations/t_sync_visualization.md#task_A73B065DC3834AFCA422E364A1468099" format="dita" scope="local"> locking selection </a> to freeze that visual on either the items of a table or positions of a freeform table. </p> <p>When this option is selected, a companion freeform table is created &amp;amp; hidden automatically. Analysis Workspace does this so that there is a data source for the visualization that will not likely be changed. </p> <p> </p> </td> 
   <td colname="col2"> <p>If you lock your visuals to items or positions in a table, consider deleting the table that you created the visual from if you don’t need to see the raw data in your project. The visualization will be unaffected after you delete the original table because of the hidden data source that it is dependent on. You can always modify the data source by unhiding it from the top left dot on the visualization. </p> <p>Decrease the number of visualizations in your project. Analysis Workspace is doing a lot of processing behind the scenes for each visual that you add, so prioritize the visuals that are most important to the consumer of the report and break out supporting visuals into a separate, more detailed project if needed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Complexity of visualizations (segments, metrics, filters)</b> </p> <p>The type of visualization (e.g. fallout vs a freeform table) added to a project by itself doesn’t influence project performance very much. It is the complexity of the visualization that will add to processing time. Factors that add complexity to a visualization include: </p> 
    <ul id="ul_3B91DABC8B714C25868FDA7ABDAC4279"> 
     <li id="li_AC1722BEB37B44C1981F83A83CE13F67">Range of data requested, as mentioned above </li> 
     <li id="li_319785136D364B869FB216A2E77AEE55">Number of segments applied; for instance, segments used as rows of a freeform table </li> 
     <li id="li_15F1A7F8EB274F518D1DFEA270E648B4">Use of intricate segments, such as sequential segments </li> 
     <li id="li_DF8440A3201D4FC8B0B89B57E3963784">Number of metrics included, especially calculated metrics that use segments </li> 
     <li id="li_92885BEB3C6F4508AE1D6894519DFD7F">Filters applied to rows in freeform tables </li> 
    </ul> <p> </p> </td> 
   <td colname="col2"> <p>If you notice that your projects aren't loading as quickly as you'd like, try replacing some segments with eVars and filters, where possible. Think about opportunities to reduce the complexity of your segments as well. For example, “contains” operators in segments add more to processing time than “equals”. </p> <p>If you find yourself constantly using segments and calculated metrics for data points that are important to your business, consider improving your implementation to capture these data points more directly. The use of a tag manager like DTM and Adobe’s processing rules can make implementation changes quick &amp;amp; easy to implement. </p> <p>In addition, using <a href="https://marketing.adobe.com/resources/help/en_US/reference/classifications.html" format="html" scope="external"> classifications </a> can help consolidate many values into concise groups from which you can then create segments. Segmentation on classification groups provides performance benefits over segments that contain many OR statements or “contains” criteria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Number of panels </b> </p> <p>One panel can contain many visualizations, and as a result, the number of panels can also influence the overall responsiveness of Analysis Workspace </p> </td> 
   <td colname="col2"> <p>Don’t try to add everything into one project, but rather create distinct projects that serve a specific purpose or group of stakeholders. Use tags to organize projects into key themes and share related projects with groups of stakeholders. </p> <p>If more organization of projects is desired, remember that <a href="https://www.youtube.com/watch?v=6IOEewflG2U" format="https" scope="external"> direct linking </a> to your project is an option. Create an internal index of projects so that stakeholders can more easily find what they need. Additionally, Adobe is actively looking into bringing more organization options to Analysis Workspace. </p> <p>If many panels are needed in one Workspace, collapse panels before saving and sharing. When a project is loaded, Analysis Workspace will only load content for the expanded panels. Collapsed panels will not be loaded until the user expands them. This approach helps in two ways: </p> 
    <ul id="ul_5533C2418D364120BEF5C388E2DB8216"> 
     <li id="li_F558D6C90AC14875AC9C59ECEFFFF461">Collapsed panels save on overall load time of a project </li> 
     <li id="li_CD0A51F11CB146918A79F4622FAA700E">Collapsed panels are a great way to organize your projects in a logical way for the consumer of the report </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Report suite size</b> </p> <p>The size of the report suite may seem like a driving factor, but in reality it only plays a small role in project performance due to how Adobe handles data processing </p> <p> </p> </td> 
   <td colname="col2"> <p> N/A </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Number of people concurrently accessing Analysis Workspace</b> </p> <p>The number of people accessing Analysis Workspace or specific projects at the same time does not have a material effect on Analysis Workspace performance. </p> <p> </p> </td> 
   <td colname="col2"> <p>N/A </p> </td> 
  </tr> 
 </tbody> 
</table>

