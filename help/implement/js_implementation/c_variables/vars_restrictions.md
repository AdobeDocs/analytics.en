---
description: Characters and strings that are never allowed in JavaScript variables.
keywords: Analytics Implementation
seo-description: Characters and strings that are never allowed in JavaScript variables.
seo-title: Illegal JavaScript characters
solution: Analytics
subtopic: Variables
title: Illegal JavaScript characters
topic: Developer and implementation
uuid: 5121bc6f-b107-4a9b-b7db-932ea9551631
index: y
internal: n
snippet: y
---

# Illegal JavaScript characters

Characters and strings that are never allowed in JavaScript variables.

* Tab (0x09) 
* Carriage return (0x0D) 
* Newline (0x0A) 
* ASCII characters with codes above 127 (unless multi-byte characters are enabled and *`charSet`* is populated appropriately) 
* HTML tags (e.g. <b></b> or &#153)

Many variables, most notably products, hierarchy, and events, have additional limitations or syntax requirements. For individual variable limitations and syntax requirements, see the section corresponding to the *`s_account`* variable parameters. 
