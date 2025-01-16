---
title: Basic functions
description: The Calculated Metrics Builder lets you apply statistical and mathematical functions to build Advanced Calculated Metrics.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
---
# Basic functions


The [Calculated metrics builder](cm-workflow/cm-build-metrics.md) lets you apply statistical and mathematical functions. This article documents alphabetical list of the functions and their definitions.

>[!NOTE]
>
>Where [!DNL metric] is identified as an argument in a function, other expressions of metrics are also allowed. For example, [COLUMN MAXIMUM(metrics)](#column-maximum) also allows for [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum).



## Table functions versus row functions 

A table function is one where the output is the same for every row of the table. A row function is one where the output is different for every row of the table. 

Where applicable and relevant, a function is annotated with the type of function: [!BADGE Table]{type="Neutral"} or [!BADGE Row]{type="Neutral"} 

## What does the include-zeros parameter mean?

It tells whether to include zeros in the computation. Sometimes zero means *nothing*, but sometimes it's important.

For example, if you have a Revenue metric, and then add a Page Views metric to the report, there are suddenly more rows for your revenue, which are all zero. You probably don't want that additional metric to affect any **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)**, and more calculations that you have in the revenue column. In this case, you would check the `include-zeros` parameter.

An alternative scenario is that you have two metrics of interest and one has a higher average or minimum because some of the rows are zeros.  In that case, you can opt not to check the parameter to include zeros



## Absolute Value {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="Absolute Value"
>abstract="Returns the absolute value of a number. The absolute value of a number is the number with a positive value."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE Row]{type="Neutral"} Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

| Argument | Description |
|---|---|
| metric | The metric for which you want to calculate the absolute value. |


## Column Maximum {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="Column Maximum"
>abstract="Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

| Argument | Description |
|---|---|
| metric | Requires at least one metric but can take any number of metrics as parameters. |
| include_zeros | Whether or not to include zero values in the calculations. | 


## Column Minimum {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="Column Minimum"
>abstract="Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

| Argument | Description |
|---|---|
| metric| Requires at least one metric but can take any number of metrics as parameters.|
| include_zeros | Whether or not to include zero values in the calculations. |


## Column Sum {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="Column Sum"
>abstract="Adds all numeric values for a metric within a column (across the elements of a dimension)."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

Adds all numeric values for a metric within a column (across the elements of a dimension).

| Argument | Description |
|---|---|
| metric | Requires at least one metric but can take any number of metrics as parameters.|


## Count {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="Count"
>abstract="Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension)."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Table]{type="Neutral"} Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

| Argument | Description |
|---|---|
| metric| The metric you want to count.|


## Exponent {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="Exponent"
>abstract="Returns e raised to the power of a given number. The constant e equals 2.71828182845904, the base of the natural logarithm. EXPONENT is the inverse of LN, the natural logarithm of a number."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE Row]{type="Neutral"} Returns e raised to the power of a given number. The constant e equals 2.71828182845904, the base of the natural logarithm. EXPONENT is the inverse of LN, the natural logarithm of a number.

| Argument | Description |
|---|---|
| metric | The exponent applied to the base e.|


## Mean {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="Mean"
>abstract="Returns the arithmetic mean, or average, for a metric in a column"

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} Returns the arithmetic mean, or average, for a metric in a column.

| Argument | Description |
|---|---|
| metric | The metric for which you want to calculate the average.|
| include_zeros | Whether or not to include zero values in the calculations. |


## Median {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="Median"
>abstract="Returns the median for a metric in a column. The median is the number in the middle of a set of numbers. That is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} Returns the median for a metric in a column. The median is the number in the middle of a set of numbers. That is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

| Argument | Description |
|---|---|
| metric | The metric for which you want to calculate the median.|
| include_zeros | Whether or not to include zero values in the calculations. |


## Modulo {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="Modulo"
>abstract="Returns the remainder after dividing x by y using Euclidean division. "

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Returns the remainder after dividing x by y using Euclidean division. 

| Argument | Description |
|---|---|
| metric_X | The first metric that you would like to divide. |
| metric_Y | The second metric that you would like to divide. |

### Examples

The return value has the same sign as the input (or is zero).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

To ensure you always get a positive number, use

```
MODULO(MODULO(x,y)+y,y)
```

## Percentile {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="Percentile"
>abstract="Returns the nth percentile, which is a value between 0 and 100. When n < 0, the function uses zero. When n > 100, the function returns 100."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE Table]{type="Neutral"} Returns the nth percentile, which is a value between 0 and 100. When n < 0, the function uses zero. When n > 100, the function returns 100.

| Argument | Description |
|---|---|
| metric | The percentile value in the range 0 to 100, inclusive. |
| k | The metric column that defines relative standing. |
| include_zeros | Whether or not to include zero values in the calculations. |



## Power Operator {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="Power Operator"
>abstract="Returns x raised to the y power."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

Returns x raised to the y power.

| Argument | Description |
|---|---|
| metric_X | The metric that you would like to raise to the metric_Y power. |
| metric_Y | The power you would like to raise metric_X to. |


## Quartile {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="Quartile"
>abstract="Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Table]{type="Neutral"} Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. [COLUMN MINIMUM](#column-minimum), [MEDIAN](#median), and [COLUMN MAXIMUM](#column-maximum) return the same value as [QUARTILE](#quartile) when quartile is equal to `0` (zero), `2`, and `4`, respectively.

| Argument | Description |
|---|---|
| metric | The metric for which you want to calculate the quartile value. |
| quartile | Indicates which quartile value to return. |
| include_zeros | Whether or not to include zero values in the calculations. |


## Round {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="Round"
>abstract="Round without a *number* parameter is the same as round with a *number* parameter of 0, namely round to the nearest integer.  With a *number* parameter, ROUND returns the *number* digits to the right of the decimal.  If *number* is negative, it returns 0's to the left of the decimal."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

Round without a *number* parameter is the same as round with a *number* parameter of 0, namely round to the nearest integer.  With a *number* parameter, ROUND returns the *number* digits to the right of the decimal.  If *number* is negative, it returns 0's to the left of the decimal.

| Argument | Description |
|---|---|
| metric | The metric that you want to round. |
| number | How many digits to the right of the decimal to return. (If negative returns zeros to the left of the decimal). |

### Examples

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## Row Count {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="Row Count"
>abstract="Returns the count of rows for a given column (the number of unique elements reported within a dimension). *Uniques exceeded* is counted as 1."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

Returns the count of rows for a given column (the number of unique elements reported within a dimension). *Uniques exceeded* is counted as 1.


## Row Max {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="Row Max"
>abstract="Maximum of the columns of each row."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

Maximum of the columns of each row.

| Argument | Description |
|---|---|
| metric | Requires at least one metric but can take any number of metrics as parameters. |
| include_zeros | Whether or not to include zero values in the calculations. |


## Row Min {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="Row Min"
>abstract="Minimum of the columns of each row."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

Minimum of the columns of each row.

| Argument | Description |
|---|---|
| metric | Requires at least one metric but can take any number of metrics as parameters. |
| include_zeros | Whether or not to include zero values in the calculations. |



## Row Sum {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="Row Sum"
>abstract="Sum of the columns of each row."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

Sum of the columns of each row.

| Argument | Description |
|---|---|
| metric | Requires at least one metric but can take any number of metrics as parameters. |


## Square Root {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="Square Root"
>abstract="Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE Row]{type="Neutral"} Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

| Argument | Description |
|---|---|
| metric | The metric for which you want to calculate the square root. |


## Standard Deviation {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="Standard Deviation"
>abstract="Returns the standard deviation, or square root of the variance, based on a sample population of data."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} Returns the standard deviation, or square root of the variance, based on a sample population of data.

| Argument | Description |
|---|---|
| | The metric for which you want to calculate the standard deviation.|
| include_zeros | Whether or not to include zero values in the calculations. |


## Variance {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="Variance"
>abstract="Returns the variance based on a sample population of data."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} Returns the variance based on a sample population of data.

| Argument | Description |
|---|---|
| metric | The metric for which you want to calculate the variance.|
| include_zeros | Whether or not to include zero values in the calculations. |


The equation for VARIANCE is:

![](assets/variance_eq.png){width="100"}

Where *x* is the sample mean, [MEAN(*metric*)](#mean), and *n* is the sample size.


To calculate a variance, you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average, you go through each entry and do the following:

1. Subtract the average from the number.

1. Square the result.

1. Add that to the total.

Once you have iterated over the entire column, you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In the example of the following three-item column:

| column |
|:---:|
| 1 |
| 2 |
| 3 |

The average of this column is 2. The variance for the column is ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3.

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->