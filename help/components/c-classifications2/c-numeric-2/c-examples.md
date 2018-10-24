---
description: Examples to provide guidance for importing numeric 2 classifications.
seo-description: Examples to provide guidance for importing numeric 2 classifications.
seo-title: Examples
solution: Analytics
subtopic: Classifications
title: Examples
topic: Admin tools
uuid: 9e68972a-5e64-45a0-841d-e2b9f5f0f665
index: y
internal: n
snippet: y
---

# Examples

Examples to provide guidance for importing numeric 2 classifications.

<!-- 

c_example_1__rate.xml

 -->

In this case, you created the classification on the [!UICONTROL Classification Conversion] manager and want to import the January values: 

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_jan_var  |  | .2  |
|  Product2  | Text2  | Cost2_jan_var  |  | .3  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/01/01 - 2010/01/31  | revenue  | revenue  |
|  2010/01/01 - 2010/01/31  | revenue  | revenue  |

In January, Product1 had a cost of 20% of its revenue (shown in ~MyCost^~value~) and Product2 had a cost of 30% of its revenue. Because you are importing a new row, ~MyCost^~id~ is blank.

## Result {#section_E0569289C9B34C479C7D2CD9ECBF866E}

An example of output from the report is shown here:

Period: Jan 2010

Report: Products 

|  Products  | Revenue  | MyCost  |
|---|---|---|
|  Product1  | $10,000.23  | $2000.05  |
|  Product2  | $9,000.04  | $2700.01  |

<!-- 

c_example_2__rate.xml

 -->

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_jan_var  | 1  | .2  |
|  Product2  | Text2  | Cost2_jan_var  | 2  | .3  |
|  Product1  | Text1  | Cost1_feb_var  |  | .15  |
|  Product2  | Text2  | Cost2_feb_var  |  | .25  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/01/01 - 2010/01/31  | revenue  | revenue  |
|  2010/01/01 - 2010/01/31  | revenue  | revenue  |
|  2010/02/01 - 2010/02/28  | revenue  | revenue  |
|  2010/02/01 - 2010/02/28  | revenue  | revenue  |

In February, the user’s cost for Product1 went down to 15% of the revenue, and Product2 went down to 25% of its revenue.

## Result {#section_23DF5353AC1B478C88647F222703352C}

An example of output from the report is shown here:

Period: Jan 2010

Report: Products 

|  Products  | Revenue  | MyCost  |
|---|---|---|
|  Product1  | $10,000.23  | $2000.05  |
|  Product2  | $9,000.04  | $2700.01  |

Period: Feb 2010

Report: Products 

|  Products  | Revenue  | MyCost  |
|---|---|---|
|  Product1  | $15,500.75  | $2325.11  |
|  Product2  | $12,300.52  | $3075.13  |

Period: Jan 1, 2010 - Feb 28, 2010

Report: Products 

|  Products  | Revenue  | MyCost  |
|---|---|---|
|  Product1  | $25,500.98  | $4325.16  |
|  Product2  | $21,300.56  | $5,775.14  |

<!-- 

c_example_3__fixed.xml

 -->

You would therefore import the following data: 

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_mar_fixed  |  | 3000.00  |
|  Product2  | Text2  | Cost2_jan_fixed  |  | 2000.00  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/03/01 - 2010/03/31  | fixed  | none  |
|  2010/03/01 - 2010/03/31  | fixed  | none  |

## Result {#section_674B57ADB8284B878F9E670038C31464}

An example of output from the report is shown here:

Period: Mar 2010

Report: Products 

|  Products  | Revenue  | MyCost  |
|---|---|---|
|  Product1  | $11,023.75  | $3000.00  |
|  Product2  | $8,000.12  | $2000.00  |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

In this example, you add a $500 shipping charge to Product1 for January, and a $600 shipping charge to February. 

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_jan_var  | 1  | .2  |
|  Product1  | Text1  | Cost2_jan_fixed  |  | 500  |
|  Product1  | Text1  | Cost1_feb_var  | 2  | .15  |
|  Product1  | Text1  | Cost2_feb_fixed  |  | 600  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/01/01 - 2010/01/31  | revenue  | revenue  |
|  2010/01/01 - 2010/01/31  | fixed  | none  |
|  2010/02/01 - 2010/01/31  | revenue  | revenue  |
|  2010/02/01 - 2010/01/31  | fixed  | none  |

The rows that were previously imported have an ID, which indicates that they are not new costs.

## Result {#section_2096084176614B9AA60F97D5853CB9EA}

An example of output from the report is shown here:

Period: Jan 2010

Report: Products 

|  Products  | Revenue  | MyCost  |
|---|---|---|
|  Product1  | $10,000.23  | $2500.05  |

>[!NOTE]
>
>This feature is for advanced users to approximate values. The resulting information should not be treated as exact values.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

The following illustrates this example: 

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_mar_var  |  | 1  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/03/01 - 2010/03/31  | order  | order  |

## Result {#section_39E24ECCC3B34C9AADC25572662750E5}

An example of output from the report is shown here:

Period: Mar 2010

Report: Products by Page 

|  Products by Page  | Orders  | MyCost  |
|---|---|---|
|  Product1  | 1000  | $1000.00  |
|  Home Page  | 600  | $600  |
|  Shopping Cart  | 400  | $400  |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_mar_fixed  |  | 3000.00  |
|  Product2  | Text2  | Cost2_mar_fixed  |  | 2000.00  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/03/01 - 2010/03/31  | fixed  | none  |
|  2010/03/01 - 2010/03/31  | fixed  | none  |

## Result {#section_7F5F5970077D4E14A5DC91495E23540D}

An example of output from the report is shown here:

Period: Mar 2010

Report: Products by Page 

|  Products by Page  | Orders  | MyCost  |
|---|---|---|
|  Product1  | 1000  | $3000.00  |
|  Home Page  | 600  | 0  |
|  Shopping Cart  | 400  | 0  |

<!-- 

c_example_7__fixed_hinge.xml

 -->

In this case, you would import the following data: 

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_mar_fixed  |  | 3000.00  |
|  Product2  | Text2  | Cost2_mar_fixed  |  | 2000.00  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/03/01 - 2010/03/31  | fixed  | revenue  |
|  2010/03/01 - 2010/03/31  | fixed  | revenue  |

## Result {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

An example of output from the report is shown here:

Period: Mar 2010

Report: Products by Page 

|  Products by Page  | Orders  | MyCost  |
|---|---|---|
|  Product1  | 1000  | $3000.00  |
|  Home Page  | 600  | $1800.00  |
|  Shopping Cart  | 400  | $1200.00  |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

In this case, you import the following file data: 

|  Key  | MyText  | ~MyCost  | ~MyCost^~id~  | ~MyCost^~value~  |
|---|---|---|---|---|
|  Product1  | Text1  | Cost1_mar_fixed  |  | 3  |

|  ~MyCost^~period~  | ~MyCost^~rate~  | ~MyCost^~hinge~  |
|---|---|---|
|  2010/03/01 - 2010/03/31  | order  | revenue  |

## Result {#section_6E2604D9A3B0455585EFF0F80FF54127}

An example of output from the report is shown here:

Period: Mar 2010

Report: Products by Page 

|  Products by Page  | Orders  | MyCost  |
|---|---|---|
|  Product1  | 1000  | $3000.00  |
|  Home Page  | 600  | $1,000.00  |
|  Shopping Cart  | 400  | $2,000.00  |

