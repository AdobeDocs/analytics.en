---
description: Examples, notes, and syntax notes about using date ranges in customized expressions.
title: Examples of date ranges using customized expressions
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: User, Admin
exl-id: d936dd4e-d330-4ed9-a979-3273397d7d92
---
# Examples of date ranges using customized expressions

Examples, notes, and syntax notes about using date ranges in customized expressions.

The table assumes that today's date is Monday, November 10, 2011, using the Gregorian calendar.

|  Example  | Date Range  | Customize Expression  | Date Range of Report  |
|---|---|---|---|
|  | | **From** | **To** | |
|  1  | Two weeks ago  | cw-2w  | cw-1w-1d  | 26 Oct to 1 Nov  |
|  2  | First 3 days of the fifth month of last year  | cy-1y+4m  | cy-1y+4m+2d  | 1 May to 3 May 2010  |
|  3  | One full week, starting 4 weeks ago  | cw-4w  | cw-3w-1d  | 12 Oct to 18 Oct  |
|  4  | Last week in the previous year  | cw-53w  | cw-52w-1d  | Nov to 9 Nov 2010  |
|  5  | One month starting 2 months ago  | cm-2m  | cm-1m-1d  | 1 Sept to 30 Sept  |
|  6  | 12 months ago in the previous year  | cm-12m  | cm-11m-1d  | 1 Nov to 30 Nov 2010  |

## Notes on examples {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Example 1**

If today is Monday, November 10, 2011, take the current date and subtract one week to obtain the last full week of October.

**Example 2**

Add four months to the beginning of the year (the month of January) to get the month of May; add two days to the first day of the month to get the third day of the month.

## Syntax notes {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Customized expressions covering most date ranges can be created by linking two terms with an operator. A term is a combination of an integer multiplier and a period abbreviation. An example of a term is 18d. An example of an operator is +.

* White space is not allowed between operators and terms.
* Use only these abbreviations: cd cw cm cq cy d w m q y 
* The best practice is to use the same date reference in the start date and in the end date: cd, cd, or cw, cw, or cy, cy. Mixing date references can lead to invalid dates at certain times of the year.
* Valid multiples of the abbreviations d w m q y are formed by means of integers ( 1 2 3 ... ) prepended to the abbreviation, such as 53d 3w 5q 9m 2y
* Non-integer numbers are not allowed.
* Do not prepend the abbreviation with only a zero. For example, 0w is not allowed.
* The following operators are used to concatenate abbreviations: + - 
* Because date ranges must be reckoned relative to the current period, the first term in an expression always begins with c.
