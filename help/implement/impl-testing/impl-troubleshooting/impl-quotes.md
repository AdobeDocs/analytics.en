---
description: When you input values into a variable, there are a few best practices to follow.
keywords: Analytics Implementation
seo-description: When you input values into a variable, there are a few best practices to follow.
seo-title: Using quotes
solution: Analytics
subtopic: Troubleshooting
title: Using quotes
topic: Developer and implementation
uuid: 9f09c48b-7ae5-441e-8635-fd6bdc2e94c7
index: y
internal: n
snippet: y
---

# Using quotes

When you input values into a variable, there are a few best practices to follow.

You can use single quotes or double quotes, make sure you are consistent. If you are using single quotes, always use single quotes. If you are using double quotes, always use double quotes. Both of the examples below are correct. 

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

Make sure that you have smart quotes turned off. If you are using single quotes, and you have an apostrophe in the variable value, JavaScript interprets the apostrophe as a single quote. This means it is the end of the string. Consider the following example: 

```js
s.pageName='John's Home Page'
```

In this case, JavaScript would interpret the apostrophe (which is also a single quote) in "John's" to be the end of the string. Since ''s Home Page" has no meaning in JavaScript, it causes an error that prevents the image request from occurring. Either of the following examples would work: 

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

In the first example, you can escape the apostrophe by inserting a backslash (\) immediately before it. This tells JavaScript that the apostrophe is not ending the string, but rather is part of it. The string then ends as intended, at the closing single-quote. The second example uses double-quotes around the entire string. In this case, a single-quote cannot indicate the end of the string. The same is true if a double-quote is part of the string. A value of s.pageName="Team Says "We Win!"" would be incorrect because of the use of double-quotes within the string, as well as surrounding it. This would be correct if entered as s.pageName="Team Says \"We Win!\"". 
