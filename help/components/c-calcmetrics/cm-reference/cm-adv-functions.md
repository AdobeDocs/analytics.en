---
description: Access these functions by checking Show Advanced in the Functions drop-down list.
title: Reference  advanced functions
uuid: 7d1071b9-1737-4b7c-b318-87907dae5619
exl-id: a6d0c2ad-864d-4cab-84e0-dd6ce0a4c6b1
---
# Reference: advanced functions

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## Table Functions versus Row Functions {#section_8977BE40A47E4ED79EB543A9703A4905}

A table function is one where the output is the same for every row of the table. A row function is one where the output is different for every row of the table.

## What does the Include-Zeros parameter mean? {#section_C7A2B05929584C65B308FD372CB8E8E3}

It tells whether to include zeros in the computation. Sometimes zero means "nothing", but sometimes it's important.

For example, if you have a Revenue metric, and then add a Page Views metric to the report, there are suddenly more rows for your revenue which are all zero. You probably don't want this to affect any MEAN, MIN, QUARTILE, etc. calculations that you have on the revenue column. In this case, you would check the include-zeros parameter.

On the other hand, if you have two metrics that you are interested in, it may not be fair to say that one has a higher average or minimum because some of its rows were zeros, so you would not check the parameter to include the zeros.

## AND {#concept_E14513FE464F4491AD0D4130D4EE621C}

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension) {#concept_000776E4FA66461EBA79910B7558D5D7}

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case {#section_424E3FC5092948F0A9D655F6CCBA0312}

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![](assets/approx-customers.png)

### Uniques Exceeded {#section_9C583858A9F94FF7BA054D1043194BAA}

Like Count() and RowCount(), Approximate Count Distinct() is subject to ["uniques exceeded" limits](https://experienceleague.adobe.com/docs/analytics/technotes/low-traffic.html). If the "uniques exceeded" limit is reached within a particular month for a dimension, the value is counted as 1 dimension item.

### Comparing Count Functions {#section_440FB8FB44374459B2C6AE2DA504FC0B}

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row) {#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row) {#concept_90F00DEC46BA47F8A21493647D9668CD}

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric) 
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row) {#concept_3408520673774A10998E9BD8B909E90C}

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row) {#concept_25615693312B4A7AB09A2921083502AD}

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Ceiling (Row) {#concept_A14CDB1E419B4AA18D335E5BA2548346}

Returns the smallest integer not less than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula CEILING( *Revenue*) to round revenue up to the nearest dollar, or $570.

```
CEILING(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to round.  |

## Cosine (Row) {#concept_DD07AA1FB08145DC89B69D704545FD0A}

Returns the cosine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
COS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the cosine.  |

## Cube Root {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

Returns the positive cube root of a number. The cube root of a number is the value of that number raised to the power of 1/3.

```
CBRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the cube root.  |

## Cumulative {#concept_3D3347797B6344CE88B394C3E39318ED}

Returns the sum of x for the last N rows (as ordered by the dimension, using hash values for string based fields).

If N <= 0 it uses all previous rows. Since it's ordered by the dimension it's only useful on dimensions that have a natural order like date or path length.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Cumulative Average {#concept_ABB650962DC64FD58A79C305282D3E61}

Returns the average of the last N rows.

If N <= 0 it uses all previous rows. Since it's ordered by the dimension it's only useful on dimensions that have a natural order like date or path length.

>[!NOTE]
>
>This does not work as you might expect with rate metrics like revenue/visitor: it averages the rates instead of summing revenue over the last N and summing visitors over the last N and then dividing them. Instead, use

```
cumul(revenue)/cumul(visitor)
```

## Equal {#concept_A3B97152B5F74E04A97018B35734BEEB}

Returns items that match exactly for a numeric or string value.

## Exponential Regression_ Correlation Coefficient (Table) {#concept_C18BBFA43C1A499293290DF49566D8D8}

Returns the correlation coefficient, *r*, between two metric columns ( *metric_A* and *metric_B*) for the regression equation .

```
CORREL.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Exponential Regression: Intercept (Table) {#concept_0047206C827841AD936A3BE58EEE1514}

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Exponential Regression: Slope (Table) {#concept_230991B0371E44308C52853EFA656F04}

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Floor (Row) {#concept_D368150EC3684077B284EE471463FC31}

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than {#concept_A83734A0C0C14646B76D2CC5E677C644}

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row) {#concept_79DD5681CE9640BDBA3C3F527343CA98}

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row) {#concept_96230731600C45E3A4E823FE155ABA85}

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row) {#concept_BD249013732F462B9863629D142BCA6A}

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tangent.  |

## IF (Row) {#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

Returns items whose numeric count is less than the value entered.

## Less Than or Equal {#concept_99D12154DE4848B1B0A6327C4322D288}

Returns items whose numeric count is less than or equal to the value entered.

## Linear regression_ Correlation Coefficient {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b. Returns b.

## Linear regression_ Predicted Y {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b. Returns Y.

## Linear regression_ Slope {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b. Returns a.

## Log Base 10 (Row) {#concept_4C65DF9659164261BE52AA5A95FD6BC1}

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table) {#concept_F3EB35016B754E74BE41766E46FDC246}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table) {#concept_75A3282EDF54417897063DC26D4FA363}

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Log Regression: Predicted Y (Row) {#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Log regression: Slope (Table) {#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the independent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Natural Log {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT {#concept_BD954C455A8148A3904A301EC4DC821E}

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal {#concept_EC010B7A9D2049099114A382D662FC16}

Returns all items that do not contain the exact match of the value entered.

## Or (Row) {#concept_AF81A33A376C4849A4C14F3A380639D2}

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi {#concept_41258789660D4A33B5FB86228F12ED9C}

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table) {#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table) {#concept_7781C85597D64D578E19B212BDD1764F}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Power regression: Predicted Y (Row) {#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Power regression: Slope (Table) {#concept_5B9E71B989234694BEB5EEF29148766C}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Correlation coefficient (Table) {#concept_9C9101A456B541E69BA29FCEAC8CD917}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table) {#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Predicted Y (Row) {#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the independent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table) {#concept_0023321DA8E84E6D9BCB06883CA41645}

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Reciprocal regression: Correlation coefficient (Table) {#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table) {#concept_2DA45B5C69F140EC987649D2C88F19B3}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Reciprocal regression: Predicted Y (Row) {#concept_2CF4B8F417A84FE98050FE488E227DF8}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Reciprocal regression: Slope (Table) {#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the independent data.  |
|  *metric_Y* | A metric that you would like to designate as the dependent data.  |

## Sine (Row) {#concept_21C8C3AA835947A28B53A4E756A7451E}

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation 

## T-Test {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent {#concept_C25E00CB17054263AB0460D9EF94A700}

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row) {#concept_96BEAC79476C49B899DB7E193A5E7ADD}

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z-Test {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.
