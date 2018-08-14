---
description: In addition to the standard cell formatting choices available through Excel's Format > Cells (Ctrl+1) feature, you can apply limited formatting to cell ranges with report builder. These formatting choices depend on the metric you have chosen.
seo-description: In addition to the standard cell formatting choices available through Excel's Format > Cells (Ctrl+1) feature, you can apply limited formatting to cell ranges with report builder. These formatting choices depend on the metric you have chosen.
seo-title: Format the date
solution: Analytics
title: Format the date
topic: Report builder
uuid: 450d5baa-0248-42f0-b39e-d58effcea037
index: y
internal: n
snippet: y
translate: y
---

# Format the date

After you [ add dimensions ](../../report_builder_bucket/layout/metrics_dimensions/t_add_metrics_and_dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) to the Row Labels grid, click **[!UICONTROL  Format]**. 

In the **[!UICONTROL  Format]** menu, click **[!UICONTROL  Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. For example, you can enter text that always occurs after the date (such as A.D. B.C.E. A.H. etc.). You can add text before the date, such as [!UICONTROL  Start Date] and [!UICONTROL  Start and End Date]. In addition, you can construct a custom date expression from day, month, and year abbreviations, and use a custom separator between parts of the date. All date formats must consist of three abbreviations only enclosed in brackets. 

The following table describes how you can use date abbreviations in the [!UICONTROL  Custom Format] field: 

<table id="table_FE187AC9225648DA90AA1BD9D59C67FD"> 
 <thead> 
  <tr> 
   <th class="entry"> <p>Abbreviation </p> </th> 
   <th class="entry"> <p>Meaning </p> </th> 
   <th class="entry"> <p>Example </p> <p> <i>using Wednesday, March 14, 2012</i> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> MM/dd/yyy </td> 
   <td> Full numeric date </td> 
   <td> 03/14/2012 </td> 
  </tr> 
  <tr> 
   <td> M </td> 
   <td> Number of month </td> 
   <td> 3 </td> 
  </tr> 
  <tr> 
   <td> MM </td> 
   <td> Number of month with 0 padding for months &amp;lt; 10 </td> 
   <td> 03 </td> 
  </tr> 
  <tr> 
   <td> MMM </td> 
   <td> Short name of month </td> 
   <td> Mar </td> 
  </tr> 
  <tr> 
   <td> MMMM </td> 
   <td> Long name of month </td> 
   <td> March </td> 
  </tr> 
  <tr> 
   <td> D </td> 
   <td> Long name of the date </td> 
   <td> Wednesday, March 14, 2012 </td> 
  </tr> 
  <tr> 
   <td> d </td> 
   <td> Number of day </td> 
   <td> 14 </td> 
  </tr> 
  <tr> 
   <td> dd </td> 
   <td> Number of day with 0 padding for days &amp;lt; 10 </td> 
   <td> 01 - 09 </td> 
  </tr> 
  <tr> 
   <td> ddd </td> 
   <td> Short name of day </td> 
   <td> Wed </td> 
  </tr> 
  <tr> 
   <td> dddd </td> 
   <td> Long name of day </td> 
   <td> Wednesday </td> 
  </tr> 
  <tr> 
   <td> yy </td> 
   <td> 2-digit year </td> 
   <td> 10 </td> 
  </tr> 
  <tr> 
   <td> yyyy </td> 
   <td> Full 4-digit year </td> 
   <td> 2012 </td> 
  </tr> 
 </tbody> 
</table>

