---
description: Frequently asked questions about link tracking in Activity Map.
title: Link tracking FAQ
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
---
# Link tracking FAQ

Frequently asked questions about link tracking in Activity Map.

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be collecting personally identifiable information (PII) data.** This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context. 

Here are some known cases where PII data might be collected using Activity Map Tracking: 

* `Mailto` links. A mailto link is a type of HTML link that activates the default mail client on the computer for sending an e-mail.
* `User ID` links that may show up in the header/footer of a website once the user has logged in.
* For financial institutions, the account number may be shown as a link. Clicking it will collect the text of the link.
* Healthcare websites may also have PII data shown as links. Clicking these links will collect the text of the link, thereby collecting PII data.

<table id="table_0951EAC617344156BAE43000CCD838AF">
 <tbody>
  <tr>
   <td colname="col1"> <b>Q: When does link tracking occur?</b> </td>
   <td colname="col2"> A: Activity Map link and region identification occurs when users click on a page. </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Q: What is tracked by default?</b> </td>
   <td colname="col2"> A: If a click event occurs on an element, the element has to pass some checks to determine if AppMeasurement will treat it as a link. These are the checks:
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0">
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">Is this an <code>&lt;A&gt;</code> or <code>&lt;AREA&gt;</code> tag with an <code>"href"</code> property? </li>
     <li id="li_77828D24D54343E5B9A1FF7345221781">Is there an <code>"onclick"</code> attribute that sets a <code>s_objectID</code> variable? </li>
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">Is this an <code>&lt;INPUT&gt;</code> tag or <code>&lt;SUBMIT&gt;</code> button with a value or child text? </li>
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">Is this an <code>&lt;INPUT&gt;</code> tag with type <code>&lt;IMAGE&gt;</code> and a <code>"src"</code> property? </li>
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Is this a <code>&lt;BUTTON&gt;</code>? </li>
    </ul>
    If the answer is <b>Yes</b> to any of the questions above, then the element is treated as a link and will be tracked. <br/>
    &nbsp;<br/>
    Important:  Button tags with the attribute <code>type="button"</code> are not considered to be links by AppMeasurement. Consider removing <code>type="button"</code> on the button tags and adding <code>role="button"</code> or <code>submit="button"</code> instead. <br/>
    &nbsp;<br/>
    Important: An anchor tags with an <code>"href"</code> that starts with <code>"#"</code> is considered an internal target location by AppMeasurement, not a link (since you do not leave the page.) By default, Activity Map does not track these internal target locations. It tracks only links that navigate the user to a new page. </td> 
  </tr>
  <tr>
   <td colname="col1"> <b>Q: How does Activity Map track other visual HTML elements?</b> </td>
   <td colname="col2">
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5">
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Via the <code>s.tl()</code> function</b> <br/>
      &nbsp;<br/>
      If the click occurred via an <code>s.tl()</code> invocation, then Activity Map will also receive this click event and determine if a <code>linkName</code> string variable was found. During <code>s.tl()</code> execution, that <code>linkName</code> will be set as the Activity Map Link ID. The element clicked that originated the <code>s.tl()</code> call will be used to determine the region. <br/>
      &nbsp;<br/>
      Example: <br/>
      &nbsp;<br/>
      <code>&lt;img&nbsp;onclick="s.tl(true,'o','abc')"&nbsp;src="someimageurl.png"/&gt;</code><br/>
      &nbsp;
     </li>
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Via the <code>s_objectID</code> variable</b> <br/>
      &nbsp;<br/>
      Example: <br/>
      &nbsp;<br/>
      <code>&lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt;</code><br/>
      <code>&lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;</code><br/>
      <code>&nbsp;&nbsp;Link&nbsp;Text&nbsp;Here</code><br/>
      <code>&lt;/a&gt;</code> <br/>
      &nbsp;<br/>
      Important:  Note that a trailing semicolon (<code>;</code>) is required when using <code>s_objectID</code> in Activity Map.
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Q: Can you give me some examples of links that will be tracked?</b> </td>
   <td colname="col2">
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA">
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0">
      <code>&lt;a&nbsp;href="/home"&gt;Home&lt;/a&gt;</code>
     </li>
     <li id="li_76F3DB36ED734132A2386871E6EB4929">
      <code>&lt;input&nbsp;type="submit"&nbsp;value="Submit"/&gt;</code>
     </li>
     <li id="li_10CF9EDA224645169E7CDF74956DB98B">
      <code>&lt;input&nbsp;type="image"&nbsp;src="submit-button.png"/&gt;</code>
     </li>
     <li id="li_9FA171D7F49547E798DE21869F73A402">
      <code>&lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code>
     </li>
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF">
      <code>&lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/div&gt;</code>
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Q: Can you give me some examples of links that will NOT be tracked?</b> </td>
   <td colname="col2">
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547">
     <li id="li_99372060646B43EF94C13A9C682CE693">Reason: Anchor tag does not have a valid <code>"href"</code> <br/>
      &nbsp;<br/>
      <code>&lt;a&nbsp;name="innerAnchor"&gt;Section&nbsp;header&lt;/a&gt;</code><br/>
      &nbsp;
     </li>
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <code>s_ObjectID</code> nor <code>s.tl()</code> present <br/>
      &nbsp;<br/>
      <code>&lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code><br/>
      &nbsp;
     </li>
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <code>s_ObjectID</code> nor <code>s.tl()</code> present <br/>
      &nbsp;<br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;</code><br/>
      &nbsp;
     </li>
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Reason: <code>"src"</code> property is missing a form <code>input</code> element <br/>
      &nbsp;<br/>
      <code>&lt;input&nbsp;type="image"/&gt;</code><br/>
      &nbsp;
     </li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

## When does link tracking occur?

Activity Map link and region identification occurs when users click on a page.

## What is tracked by default?

If a click event occurs on an element, the element has to pass some checks to determine if AppMeasurement will treat it as a link. These are the checks:
    
* Is this an `A` or `AREA` tag with an `href` property? 
* Is there an `onclick` attribute that sets a `s_objectID` variable? 
* Is this an `INPUT` tag or `SUBMIT` button with a value or child text? 
* Is this an `INPUT` tag with type `IMAGE` and a `src` property? 
* Is this a `BUTTON`? 
    
If the answer is Yes to any of the questions above, then the element is treated as a link and will be tracked. 
     
Important:  Button tags with the attribute type="button" are not considered to be links by AppMeasurement. Consider removing type="button" on the button tags and adding role="button" or submit="button" instead. 
     
Important: An anchor tags with an "href" that starts with "#" is considered an internal target location by AppMeasurement, not a link (since you do not leave the page.) By default, Activity Map does not track these internal target locations. It tracks only links that navigate the user to a new page.

## How does Activity Map track other visual HTML elements?

a. Via the `s.tl()` function. 
    
  If the click occurred via an `s.tl()` invocation, then Activity Map will also receive this click event and determine if a `linkName` string variable was found. During `s.tl()` execution, that linkName will be set as the Activity Map Link ID. The element clicked that originated the `s.tl()` call will be used to determine the region. Example:

  ```       
  <img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
  ```
b. Via the s_objectID variable. Example: 
  
  ```     
  <img onclick="s_objectID='abc';" src="someimageurl.png"/>
      <a href="some-url.html" onclick="s_objectID='abc';" >
        Link Text Here
      </a> 
  ```

Important:  Note that a trailing semicolon (;) is required when using `s_objectID` in Activity Map.

## Can you give me some examples of links that will be tracked?

* `<a hef="/home?lang=en>Home</a>`
* `<input type="submit" value="Submit"/>`
* `<input type="image" src="submit-button.png"/>`
* ```
      <p onclick="var s_objectID='custom link id';">
        <span class="title">Current Market Rates</span>
        <span class="subtitle">1.45USD</span>
      </p>
  ```
* ```
      <div onclick="s.tl(true,'o','custom link id')">
        <span class="title">Current Market Rates</span>
        <span class="subtitle">1.45USD</span>
      </div>
  ```

## Can you give me some examples of links that will NOT be tracked?

1. Reason: Anchor tag does not have a valid `href`:
  `<a name="innerAnchor">Section header</a>`

1. Reason: Neither `s_ObjectID` nor `s.tl()` present:
      ```
      <p onclick="showPanel('market rates')">
        <span class="title">Current Market Rates</span>
        <span class="subtitle">1.45USD</span>
      </p>
      ```
1. Reason: Neither `s_ObjectID` nor `s.tl()` present:
      ```     
      <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
      <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
      <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
      ```  
     
1. Reason: "src" property is missing a form input element:

    `<input type="image"/>`
