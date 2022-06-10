---
description: The Calculated Metrics Builder lets you apply statistical and mathematical functions to build Advanced Calculated Metrics.
title: Reference  basic functions
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
---
# Reference: basic functions

The Calculated Metrics Builder lets you apply statistical and mathematical functions to build Advanced Calculated Metrics.

Here is an alphabetical list of the functions and their definitions.

>[!NOTE]
>
>Where [!DNL metric] is identified as an argument in a function, other expressions of metrics are also allowed. For example, [!DNL MAXV(metrics)] also allows for [!DNL MAXV(PageViews + Visits)].

## Table Functions versus Row Functions {#section_8977BE40A47E4ED79EB543A9703A4905}

A table function is one where the output is the same for every row of the table. A row function is one where the output is different for every row of the table.

## Absolute Value (Row) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum {#concept_B25518D717D24F82B65CDE49A153D3A3}

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation {#concept_941578534F1E4583B1BEB067C8113A21}

Power Operator

```
pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)
```

## Mean (Table) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) {#concept_183EC31208524EDB8463D986DE2E895F}

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo {#concept_DE0825D7A51643219CB01F59667EA352}

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

## Percentile (Table) {#concept_51DF57B606D14F898E5010DBA61CA979}

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

| Argument | Description |
| --- | --- |
| *metric* | The metric column that defines relative standing. |
| *k* | The percentile value in the range 0 to 100, inclusive. |

## Quartile (Table) {#concept_BFD37F0F23A24AD181407142233FA151}

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

| Argument | Description |
| --- | --- |
| *metric* | The metric for which you want the quartile value. |
| *quart* | Indicates which *value to return. |

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

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

## Row Count {#concept_0DBF5995881C47CF95F793125F3A0E2B}

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

The maximum of the columns in each row.

## Row Min {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

The minimum of the columns in each row.

## Row Sum {#concept_E9EAB0FC5233498F907E7A078698A98E}

The sum of the columns of each row.

## Square Root (Row) {#concept_6460DFA51EC24527A2317970FB76D404}

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

| Argument | Description |
| --- | --- |
| *number* | The metric for which you want the square root. |

## Standard Deviation (Table) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

Where *x* is the value of each sample (*metric*), *x&#772;* is the population mean and *n* is the population size.

```
STDEV(metric)
```

| Argument | Description |
| --- | --- |
| *metric* | The metric for which you want for standard deviation. |

## Variance (Table) {#concept_269751EDC5A34E689112AE16E04A11B0}

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

Where *x* is the value of each sample (*metric*), *x&#772;* is the population mean and *n* is the population size.

```
VARIANCE(metric)
```

| Argument | Description |
| --- | --- |
| *metric* | The metric for which you want the variance. |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.
1. Square the result.
1. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

As an example, let's say you have a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3.
