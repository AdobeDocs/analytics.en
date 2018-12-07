---
description: Frequently asked questions about link tracking in Activity Map.
seo-description: Frequently asked questions about link tracking in Activity Map.
seo-title: Link tracking FAQ
solution: Analytics
title: Link tracking FAQ
topic: Activity map
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
index: y
internal: n
snippet: y
---

# Link tracking FAQ

Frequently asked questions about link tracking in Activity Map.

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be** **collecting personally identifiable information (PII) data.** This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context. 

Here are some known cases where PII data might be collected using Activity Map Tracking: 

* `Mailto` links. A mailto link is a type of HTML link that activates the default mail client on the computer for sending an e-mail. 
* `User ID` links that may show up in the header/footer of a website once the user has logged in. 
* For financial institutions, the account number may be shown as a link. Clicking it will collect the text of the link. 
* Healthcare websites may also have PII data shown as links. Clicking these links will collect the text of the link, thereby collecting PII data. 

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Q: When does link tracking occur?</b> <p> </p> </td> 
   <td colname="col2"> A: Activity Map link and region identification occurs when users click on a page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: What is tracked by default?</b> <p> </p> </td> 
   <td colname="col2"> A: If a click event occurs on an element, the element has to pass some checks to determine if AppMeasurement will treat it as a link. These are the checks: 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">Is this an &lt;A&gt; or &lt;AREA&gt; tag with an HREF property? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">Is there an on-click attribute that sets a s_objectID variable? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">Is this an INPUT tag or SUBMIT button with a value or child text? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">Is this an INPUT tag with type IMAGE and a src property? </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Is this a &lt;Button&gt;? </li> 
    </ul> <p>If the answer is <b>Yes</b> to any of the questions above, then the element is treated as a link and will be tracked. </p> <p>Important:  Button tags with the attribute type="button" are not considered to be links by AppMeasurement. Consider removing "type='button'" on the button tags and adding role="button" or submit="button" instead. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: How does Activity Map track other visual HTML elements?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Via the <span class="codeph"> s.tl() </span> function</b> <p>If the click occurred via an s.tl invocation, then Activity Map will also receive this click event and determine if a linkName string variable was found. During s.tl execution, that linkName will be set as the Activity Map Link ID. The element clicked that originated the s.tl() call will be used to determine the region. Example: </p> <p> 
       <code>
         &lt;img&amp;nbsp;onclick="s.tl(true,'o','abc')"&amp;nbsp;src="someimageurl.png"/&gt; 
       </code> </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Via the <span class="codeph"> s_objectID </span> variable</b> <p>Example: </p> <p> 
       <code>
         &lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt; &lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;Link&nbsp;Text&nbsp;Here&lt;/a&gt;
       </code> </p> <p>Important:  Note that a trailing semicolon (;) is required when using s_objectID in Activity Map. </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Can you give me some examples of links that will be tracked?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>
        &lt;a&amp;nbsp;href="/home"&gt;Home&lt;/a&gt; 
      </code> </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>
        &lt;input&amp;nbsp;type="submit"&amp;nbsp;value="Submit"/&gt; 
      </code> </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>
        &lt;input&amp;nbsp;type="image"&amp;nbsp;src="submit-button.png"/&gt; 
      </code> </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>
        &lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>
        &lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/div&gt;
      </code> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Can you give me some examples of links that will NOT be tracked?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">Reason: Anchor tag does not have a valid href 
      <code>
        &lt;a&amp;nbsp;name="innerAnchor"&gt;Section&amp;nbsp;header&lt;/a&gt; 
      </code> </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <span class="codeph"> s_ObjectID </span> nor <span class="codeph"> s.tl() </span> present 
      <code>
        &lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <span class="codeph"> s_ObjectID </span> nor <span class="codeph"> s.tl() </span> present 
      <code>
        &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Reason: src property is missing a form input element 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

