---
description: Common errors in dynamic accounts are described in the following sections.
keywords: Analytics Implementation
seo-description: Common errors in dynamic accounts are described in the following sections.
seo-title: Common errors
solution: Analytics
subtopic: Troubleshooting
title: Common errors
topic: Developer and implementation
uuid: 04345355-60cc-4678-81c3-390c86752df1
---

# Common errors

Common errors in dynamic accounts are described in the following sections.

## Hard Coded Account {#section_FB6F89BF317F45D387C00986ACA690BC}

If the desire is to always send data to a specific report suite, set [!UICONTROL s_dynamicAccountSelection] to false (alternately, the variables may be removed altogether:

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 

```

In the case above, defaultreportsuiteid is always used after the other two lines are removed.

## Placement of Code {#section_05375CB2EF5A414794BC8209C906AEEB}

Defining *`s_account`* after the lines of code does not override the dynamic account selection, as shown below.

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 

```

In the example above, the account "anotherreportsuiteid" overrides "defaultreportsuiteid," but does not override any matches that occur in [!UICONTROL s.dynamicAccountList]. The function that evaluates [!UICONTROL s.dynamicAccountList] is actually executed much later in the .JS file.

## Multi-Suite Tagging {#section_6C014FA9B87D4622B483BCDE4281D2A9}

Multi-suite tagging may be used in conjunction with dynamic account selection, as shown below.

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 

```

## Dynamic Account Match {#section_647AB47B38D640D6BCC853FDA4E4342D}

Do not put the [!UICONTROL dynamic account match] variables in quotes. The options are displayed below.

|  Host/Domain Name  | None  |
|---|---|
|  Query String  | s.dynamicAccountMatch=(window.location.search?window.location.search:"?")  |
|  Host/Domain and Path  | s.dynamicAccountMatch=window.location.host+window.lcation.pathname  |
|  Path and Query String  | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?")  |
|  Full URL  | s.dynamicAccountMatch=window.location.href  |

