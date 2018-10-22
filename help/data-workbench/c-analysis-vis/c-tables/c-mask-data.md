---
description: Masking refers to selecting a subset of your data or a subset of the elements in a dimension.
seo-description: Masking refers to selecting a subset of your data or a subset of the elements in a dimension.
seo-title: Mask data
solution: Analytics
title: Mask data
topic: Data workbench
uuid: c5712bc3-a20b-40e2-a61f-da64399650a1
index: y
internal: n
snippet: y
---

# Mask data

Masking refers to selecting a subset of your data or a subset of the elements in a dimension.

 You mask or hide those elements that you do not want included in the analysis.

[!DNL Data workbench] provides two methods for masking dimension elements. The first method employs the options available in the [!UICONTROL Mask] menu. Using the [!UICONTROL Mask] menu options, you can use your mouse to select those elements to show or to mask, or you can show top-ranked elements when you sort the data by metric. The second method for masking dimension elements employs a search.

**To mask data**

1. Right-click an element or the label of the desired dimension and click **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Click one of the following options:

    * **[!UICONTROL Show all]** 
    * **[!UICONTROL Show selected only]** 
    * **[!UICONTROL Hide selected]** 
    * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**, or **[!UICONTROL 500]** of the displayed elements sorted by metric 
    * **[!UICONTROL Show top > All Positive]** to show only values greater than zero (0) 
    * **[!UICONTROL Display “X more”]** to show the number of currently masked elements 
    * **[!UICONTROL At least one >]***< **[!UICONTROL countable dimension name]**>* (available only when working with a denormal dimension)

      When working with a denormal dimension, this option enables you to mask a dimension by a countable dimension. When selected, the table shows only those elements that have at least one element of the countable dimension that you selected. The table displays up to 1,023 elements.

>[!NOTE]
>
>Because the Adobe [!DNL Platform] processes data in random order, when At least one masking results in more than 1,023 elements, the more common and larger elements have a greater chance of being included in the table.

When you mask by Show top or At least one, by default the order in the table corresponds to the values as affected by the selection at that time. If you later change the selection, the order does not change from the original order unless the table is resorted or you enable Dynamic Selection. When you click **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, the table is resorted each time you change the selection.

**To mask data using a search**

* You can mask data using either of the following search options:

    * Right-click an element or the label of the desired dimension, click **[!UICONTROL Mask]**, then in the [!UICONTROL Search] box type the phrase for which you want to search.

      ![](assets/mnu_Table_MaskSearch.png)

    * Right-click an element or the label of the desired dimension, click **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, then in the search box that displays in the dimension label cell, type the phrase for which you want to search.

      ![](assets/vis_Table_Mask_searchBar.png)

      As you type a search phrase, Data Workbench updates the dimension to reflect matches.

To further constrain the masking during a search, you can use any of the following methods:

* You can type “re:” in the [!UICONTROL search] box or bar to have the search phrase interpreted as a regular expression. You can use any of the syntax associated with regular expressions in your search phrase. For more information about regular expressions, see the Regular Expression appendix in the *Dataset Configuration Guide*. 
* You can type the $ symbol as the first character in your search string to find phrases that begin with the string you entered, or as the last character to find phrases that end with the string you entered. 
* You can type a space as the first character in your search string to find any words within a phrase that begin with the string you entered, or as the last character to find any words within a phrase that end with the string you entered.

Following are examples of different ways to mask a table using the string “on” in a search:

* Typing “on” displays every phrase that contains the string “on” anywhere in the phrase: “**on**line banking,” “c**on**tact buyers,” “bulli**on** coins,” “bank **on**line,” “gold opti**on**s,” and “silver bulli**on**.” 
* Typing “$on” displays every phrase that begins with the string “on”:

  “**on**line banking” and “**on**-line payment.” 

* Typing “on$” displays every phrase that ends with the string “on”:

  “silver bulli**on**” and “gold opti**on**.” 

* Typing “on” displays every phrase that contains a word that begins with the string “on”:

  “**on**line banking” and “bank **on**line.” 

* Typing “on” displays every phrase that contains a word that ends with the string “on”:

  “bulli**on** coins” and “silver bulli**on**.” 

* Using “on” displays every phrase that contains the string “on” as a word:

  “**on** line banking” and “bank **on** line.”

