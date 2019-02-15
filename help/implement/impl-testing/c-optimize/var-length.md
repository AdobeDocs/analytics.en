---
description: The length of Analytics variables can impact the size of the HTML code snippet, JavaScript library file, and image request.
keywords: Analytics Implementation
seo-description: The length of Analytics variables can impact the size of the HTML code snippet, JavaScript library file, and image request.
seo-title: Variable length
solution: Analytics
subtopic: Troubleshooting
title: Variable length
topic: Developer and implementation
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
---

# Variable length

The length of Analytics variables can impact the size of the HTML code snippet, JavaScript library file, and image request.

If a customer has many variables that are long (60 characters or more) the values can be replaced with shorter identifiers. Data classifications or VISTA rules can be used to translate the identifiers to friendly names.

>[!NOTE]
>
>Most [!DNL Analytics] variables have a maximum of 100 characters (eVars have a maximum of 255). Internet Explorer allows an overall maximum of 2,048 characters in a GET image request URL. The image request limit applies not only to the variables, but also to information about the browser, operating system, and browser plug-ins (Netscape/Mozilla only).

