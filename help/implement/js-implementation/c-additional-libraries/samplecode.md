---
description: Examples to illustrate the use of a server-generated image tag within a HTML sample page.
keywords: Analytics Implementation;variables
seo-description: Examples to illustrate the use of a server-generated image tag within a HTML sample page.
seo-title: Sample code
solution: Analytics
title: Sample code
topic: Developer and implementation
uuid: bee556ee-c14e-4e78-a036-6a18db96ce53
index: y
internal: n
snippet: y
---

# Sample code

Examples to illustrate the use of a server-generated image tag within a HTML sample page.

The table below displays the values used in the sample. 

|  Variable  | Value  |
|---|---|
|  pageName  | Order Confirmation  |
|  Current URL  | https://www.somesite.com/cart/confirmation.asp  |
|  events  | purchase,event1  |
|  c1  | Registered  |
|  purchaseID  | 0123456  |
|  products  | Books;Book Name;1;19.95  |
|  state  | CA  |
|  zip  | 90210  |
|  a random #  | 123456  |

## Example 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

The example below displays a server-side image tag. The highlighted random number prevents caching of the image.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## Example 2 {#section_726D12029583428BA853043F988ED1B8}

The example below shows a minimal JavaScript image tag.

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 

```

