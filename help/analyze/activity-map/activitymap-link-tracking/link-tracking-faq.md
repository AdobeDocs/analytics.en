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

b. Via the `s_objectID` variable. Example: 
  
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
* 

  ```

      <p onclick="var s_objectID='custom link id';">
        <span class="title">Current Market Rates</span>
        <span class="subtitle">1.45USD</span>
      </p>

  ```

* 

  ```
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
