---
description: null
seo-description: null
seo-title: Implement Analytics for Digital Assistants
title: Implement Analytics for Digital Assistants
uuid: 35e9fee5-c713-4acd-9e1e-74b0d637a92b
index: y
internal: n
snippet: y
---

# Implement Analytics for Digital Assistants

## Implement Analytics for Digital Assistants {#topic_CB8A578E23DA438F9324593BFE7C13D4}

<!-- 

<p>https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper </p> 
<p>https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html </p> 
<p>Ticket: https://jira.corp.adobe.com/browse/AN-157750 </p>

 -->

With recent advances in cloud computing, machine learning, and natural language processing, digital assistants are moving out of the dark ages of "clippy" and becoming part of everyday life. Consumers are starting to talk to their devices and expecting them to listen, understand, and respond in natural, human-like ways to phrases like, "Alexa, turn on the family room lights," or "Okay Google, What's the weather like outside?"

As these platforms become more established, brands can present their services to consumers in these same realistic and lifelike ways. For example, consumers can ask things like:

* "Alexa, ask my car when it needs an oil change." 
* "Cortana, what is the balance of my checking account?" 
* "Siri, send John $20 for dinner last night from my banking app."

This white paper provides an overview of how best to use the Adobe Analytics Cloud to measure and optimize these types of experiences. 

## Digital Experience Architecture Overview {#concept_26AC08D291724223A943C80B1C6F2333}

![](assets/Digital-Assitants.png)

Most digital assistants today follow a similar high-level architecture:

1. **Device:** There is a device (like an Amazon Echo or a phone) with a microphone that allows the user to ask a question. 
1. **Digital assistant:** That device interacts with the service that powers the digital assistant. This service is where a lot of the magic happens. It is where the speech is converted into machine understandable intents and the details of the request are parsed out. Once the user's intent is understood, the digital assistant passes the intent and details of the request to the app that handles the request. 
1. **"App":** The app can either be an app on the phone or a voice app. The app is responsible for responding to the request. It responds to the digital assistant and the digital assistant then responds to the user.

## Where to implement Analytics {#concept_F53A0566589042658DEA5B86B22C10CB}

One of the best places to implement Analytics is in the app. The app receives the [intent](../c_analytics_digital_assistants/digital-assistants-white-paper.md#section_BB339BDB5C3D40C6B5C426B0E092B48A) and the details about the intent from the digital assistant and decides how to respond.

There are two times during the life-cycle of a request that can be helpful to call the Analytics Cloud.

1. When the request is sent to the "App." If you need additional context about the user before you respond to the request, you should leverage the Audience Manager capability to get the segments that they belong to. 
1. After the response is returned from the app. If you are just interested in recording what happened with the customer for future optimization, send a request to Adobe Analytics after the response has been returned. This way you have the full context of what the request was and how the system responded.

## Analytics Implementation for Digital Assistants {#concept_CFA6129F775D45429EFCCFC59B803C63}

## New Installs {#section_FD63267479DB47C2A081244A3E65A0CC}

For some of the digital assistants you will get a notification when someone installs the skill. This is especially the case when there is authentication involved. At this time you should send Adobe an *`Install`* event by setting the context data to `a.InstallEvent=1`. Note that this is not available on all platforms but is helpful when it is present for looking at retention. The following code sample sends in *`Install`*, *`Install Date`*, and *`AppID`*.

**Code Sample**

```
GET 
/b/ss/[rsid]/0?vid=[UserID]&c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c .OSType=Alexa&pageName=install 
HTTP/1.1 
Host:  
<xref href="http: sc.omtrdc.net="" " format="http"  scope="external">
  sc.omtrdc.net 
 Cache-Control: no-cache 
</xref href="http:>
```

## Multiple Assistants or Multiple Apps {#section_81740741752E4142BE42DA4C9DDEEDF5}

It is likely that you will develop apps for multiple platforms. The best practice is to include an app ID with each request. This can be set in the `a.AppID` context data. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2

**Code Sample**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1 
Host: [prefix].sc.omtrdc.net 
Cache-Control: no-cache
```

```
 GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## User/Visitor Identification {#section_7CE70FEB43C44B90954702CA30F87D58}

The Analytics Cloud uses the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/) (ECID) service to tie interactions across time to the same person. Most of the digital assistants will return a *`userID`* that you can use to keep the activity for different users separate in the ECID service. In most cases, this is what you should pass in as the ECID service. Some platforms return a *`userID`* that is longer than the 100 characters that the Analytics limit allows. If that is the case, Adobe recommends that you hash the *`userId`* to a fixed-length value using a standard hashing algorithm, such as MD5 or Sha1.

While you can use the ECID service for this, doing so provides value only if you are trying to map ECIDs across different devices (e.g. Web to Digital Assistant). If your app is a mobile app (e.g. a deep link) you should use the SDK as is and send the information along. The *`userID`* can be attached to the ECID service using the setCustomerID method, allowing for better device stitching. However, if your app is a service, use the *`userID`* provided by the service as the ECID, as well as setting it in the setCustomerID. This allows you to see how people are using the digital assistant over time.

**Code Sample**

```
GET /b/ss/[rsid]/0?vid=[UserID]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Sessions {#section_BA4F996F976043B8993F2F7D24FE27FB}

Because digital assistants are conversational, they often have the concept of a session. For example:

**Consumer:** "Ok Google, call a cab for me"

**Google:**: "Sure, what time would you like?"

**Consumer:** "8:30pm"

**Google:** "Sounds good, the Driver will be by at 8:30pm"

These sessions are important to keep in context. They help collect more details and make the digital assistants more natural.

When implementing Analytics on a conversation, there are two things you should do when a new session is started:

1. **Reach out to Audience Manager:** Get the relevant segments that a user is a part of so that you can customize the response. (For example, this person currently qualifies for the multi-channel discount.) 
1. **Send in a new session or launch event:** When you send the first response to Analytics, include a launch event. Usually, this can be sent by setting context data of `a.LaunchEvent=1`.

**Code Sample for Launch**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Intents {#section_BB339BDB5C3D40C6B5C426B0E092B48A}

Each of the digital assistants has algorithms that detect intents and then passes the intent down to the "App" so that the app knows what to do. These intents are a succinct representation of the request.

For example, if a user says, "Siri, Send John $20 for dinner last night from my banking app," the intent might be something like *`sendMoney`*.

By sending in each of these requests as an eVar, you will be able to run pathing reports on each of the intents for conversational apps. You will also want to make sure the "App" can handle requests without an intent. We recommend passing in *`No Intent Specified`* as opposed to leaving the value blank.

**Code Sample**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

or

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Parameters/Slots/Entities {#section_041CD1730F9E4096BE75DFF2CC810852}

In addition to the intent the digital assistant will often have a set of key value pairs that give the details of the intent. These are called slots, entities or parameters. For example:

"Siri, Send John $20 for dinner last night from my banking app" would have the following parameters:

* Who = John 
* Amount = 20 
* Why = Dinner

There is usually a finite number of these with your app. To track these in Analytics, send them into context data and then map each of the parameters to an eVar.

**Code Sample**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Session {#section_17D69D6B298E46E88E175F62F1ACD831}

Although not all apps will be revenue generating, it is important to think about what success looks like and include some measurements for it. Adobe Analytics can measure revenue, ad-impressions and other forms of success along with the user behavior.

## Error States {#section_E8EFF8D610B24DC899C34E50B058864D}

Sometimes the Digital Assistant will provide the app with inputs that it doesn't know how to handle. For example.

"Siri, Send John 20 bags of coal for dinner last night from my banking app"

When this happens the app should ask for clarification. Additionally when it is responding to a request like this you should send Analytics an event that indicates the App has an error state along with an evar that specifies what type of error occurred.

Be sure to include errors where the inputs are not correct and errors where the "App" had a problem.

**Code Sample**

```
GET /b/ss/[rsid]/0/?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent] HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Device Capabilities {#section_6770D82A3B0E4AD5A2172A7E67B0DF20}

While most of the platforms don't expose the actual device that the user spoke too. They do expose the capabilities of the device as the available interfaces (e.g. Audio, Screen, Video, etc). This is useful information because it defines the types of content that can be used when interacting with your users. When measuring the interfaces it is best to concatenate them (in alphabetical order).

Example: `:Audio:Camera:Screen:Video:`

Notice the trailing and leading colons. These help when creating segments (for example, give me all interactions with `:Audio:` capabilities).

Amazon Capabilities: [https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)

Google Capabilities: [https://developers.google.com/actions/assistant/surface-capabilities](https://developers.google.com/actions/assistant/surface-capabilities) 

## Analytics Reporting for Digital Assistants {#concept_265BC8E99C5545D0A9B9412C11EE58CC}

Once your Digital Assistant App is implemented you can use the full power of Adobe Analytics with it. Below are just a few examples of the things you can do with Analytics.

## Monitoring Intents {#section_6632D9F2EF9045A7A1A4263D3561C78F}

Most Apps have several intents and different things you can do. You could easily use Analysis Workspace to keep track of the top intents by instances and by users

<!-- 

<p>--- Image of Intents --- </p>

 -->

This lets you see which features are being used most often and can give you a view into the adoption of new features.

## Requests with Errors {#section_CF1A79003E784F88A03F4EEF6CDC7A7C}

You will be able to monitor errors to see if there are common places where users are getting having problems.

<!-- 

<p>--- Image of Errors --- </p>

 -->

## Flow Between Events {#section_08FA8EBD384D41ED8CA52EFE438C8CD2}

One of the most powerful things to do is look at the flow of intents. This is helpful in two ways. First, you can look within a session for how people flow between intents in a conversation. Second, you can look at how people flow between intents over longer time frames to see how their usage of the "App" is evolving. 

## Example {#concept_2B13D5E7A8E042D1A4B7BB80BBAACD12}

**Pre-installed app** 

<table id="table_70BF4E41D0BE4482BD925FB3A1768CE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Person </th> 
   <th colname="col2" class="entry"> Device Response </th> 
   <th colname="col3" class="entry"> Action / Intent </th> 
   <th colname="col4" class="entry"> Get Request </th> 
   <th colname="col5" class="entry"> Analytics Data </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Play Spoofify </p> </td> 
   <td colname="col2"> <p> "okay playing Spoofify" </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.a.LaunchEvent=1&amp;c.Intent=Play&amp;pageName=PlayApp&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_E80B0BBEBE764023BB9B49FE5F15B918"> 
      <li id="li_9BC2CCABB0ED4246A57C37633666CDE2">Visitor ID </li> 
      <li id="li_1E7F9E979A3D49CE90899CE82C70BCD0">App Version </li> 
      <li id="li_C4BD7653B0FA47F6A3E4F1FF18138F10"># of Launches </li> 
      <li id="li_B7FA47CBD75747E8A8A25E228C90E524">Intent </li> 
      <li id="li_48274BA200704730A22C85FD682AE3B0">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change song </p> </td> 
   <td colname="col2"> <p> "okay what song do you want?" </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangeSong&amp;pageName=&nbsp;AskForSong&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_AE8CF669F06547FDA68801F20BD8CBCE"> 
      <li id="li_5A03E41891AF4F37A3BE05BC11F197BC">Visitor ID </li> 
      <li id="li_435FF7DEB169466E8C3F9258C91315D1">App Version </li> 
      <li id="li_AB2B602D9DC74B3D951A0942B6CF8B39">Intent </li> 
      <li id="li_C9F87F3BB7104C9C978BB046C5DB9092">*blank playlist </li> 
      <li id="li_FB762962468A44A18DF93488EC2CB848">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Play "My Heart Will Go On" by Celine Dion </p> </td> 
   <td colname="col2"> <p> "okay playing 'My Heart Will Go On' by Celine Dion" </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangePlaylist&amp;pageName=&nbsp;ActionPlaySong&amp;c.SongID=[012345]&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_2AFEE1E928A8499E96B1BC6C5CC21F81"> 
      <li id="li_4BDF8093373A4DA1BB24A608FAC5B7CF">Visitor ID </li> 
      <li id="li_79B4FACCD333472EB9FC1F94B904AFB4">App Version </li> 
      <li id="li_3EDAB6208CB24213A934167BD08BD1AE">Intent </li> 
      <li id="li_C8E6609F9E0A45A8AED15F73374F40B2">Song ID </li> 
      <li id="li_C4D99387C4D748189E15476F5E03BB76">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change playlist </p> </td> 
   <td colname="col2"> <p> "okay what playlist do you want?" </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangePlaylist&amp;pageName=&nbsp;AskForPlaylist&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_913CF31C3EB34BDB819AD54D28F9DE5D"> 
      <li id="li_93036A142FB34A73A95B8AB114EA99C3">Visitor ID </li> 
      <li id="li_F699CDD7866C4EB4BECFF0FAA4689736">App Version </li> 
      <li id="li_6AB1FF7ED6A247FAA8922390410F2F5F">Intent </li> 
      <li id="li_9DF30E2E1958468783FF753D014F1A5F">*blank playlist </li> 
      <li id="li_B1106A51B8CD49DD8B566B946176F854">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Play Usher </p> </td> 
   <td colname="col2"> <p> "okay playing Usher" </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangePlaylist&amp;pageName=&nbsp;ActionPlayPlaylist&amp;c.Playlist=Usher&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_B70E7C9BEFA54C2FA8B7485F9BC7CEE7"> 
      <li id="li_2B0319D20189497D8C9981F871D4FBC4">Visitor ID </li> 
      <li id="li_78C28F34FC7C41589EB111ADCC5A0D66">App Version </li> 
      <li id="li_8ACF819CF80E4E8F942E0903DF75AE33">Intent </li> 
      <li id="li_49F407E43F474356A5F131F82B6C4EB9">Playlist </li> 
      <li id="li_7380EC51B0DE420EB5DD48BCE21B0567">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Turn music off </p> </td> 
   <td colname="col2"> <p> *no response, music turns off </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=Off&amp;pageName=TurnsOffMusic&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BCA19F2A98CC42788A23E668B260F553"> 
      <li id="li_12A9DA8684B2479D90F3C357AE4F1D15">Visitor ID </li> 
      <li id="li_9E543F7F12D247D0900E5B1BE8EB0F61">App Version </li> 
      <li id="li_9627816FE3594C418EC52DAD42501BCA">Intent </li> 
      <li id="li_5D59C5D8D0F34F5193F592A867AE5639">Response </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Requires user to install app** 

<table id="table_C178E3A2C87043A0A2B8C365869102A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Person </th> 
   <th colname="col2" class="entry"> Device Response </th> 
   <th colname="col3" class="entry"> Action / Intent </th> 
   <th colname="col4" class="entry"> Get Request </th> 
   <th colname="col5" class="entry"> Analytics Data </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Install Spoofify </p> </td> 
   <td colname="col2"> <p> *no response </p> </td> 
   <td colname="col3"> <p> Install </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;amp;c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&amp;c.a.AppID=Spoofify1.0&amp;c.OSType=Alexa&amp;c.Intent=Install&amp;pageName=Install&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_83A7731E5EA84477906AF4BFB3B50F48"> 
      <li id="li_A23A342B0D5745B3854B90ADFDD15EB2">Visitor ID </li> 
      <li id="li_E2F89B771B5F445B995E30C7E76BF2D2">Date </li> 
      <li id="li_03378BC9365F4020B7E28461AFDCB160">Intent </li> 
      <li id="li_6E1ECC9AF55141D1857688DA6A33DEEA">OS Version </li> 
      <li id="li_A4D06A0DFBC247499D9586F6B76571C4">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Play Spoofify </p> </td> 
   <td colname="col2"> <p> "okay playing Spoofify" </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <codeblock>
       GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.a.LaunchEvent=1&amp;c.Intent=Play&amp;pageName=PlayApp&nbsp;&nbsp;HTTP/1.1 
      
&nbsp;Host:&nbsp;sc.omtrdc.net 
      
&nbsp;Cache-Control:&nbsp;no-cache 
     </codeblock> </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_8FCA2B1357A8496DAF563775F019404F"> 
      <li id="li_78E84586A5284164B5B577B68A113394">Visitor ID </li> 
      <li id="li_977915DC425A43BDA69D9F76ADFBAB0C">App Version </li> 
      <li id="li_12725E1D4540485B8A3DB2EC82C6AD4C"># of Launches </li> 
      <li id="li_5B7F4487682241C38071A7037157F473">Intent </li> 
      <li id="li_A6AC81D56BF44E07B2FC0F2740CAB237">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change song </p> </td> 
   <td colname="col2"> <p> "okay what song do you want?" </p> </td> 
   <td colname="col3"> <p>ChangeSong </p> </td> 
   <td colname="col4"> 
    <codeblock>
      GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangeSong&amp;pageName=&nbsp;AskForSong&nbsp;&nbsp;HTTP/1.1 
     
&nbsp;Host:&nbsp;sc.omtrdc.net 
     
&nbsp;Cache-Control:&nbsp;no-cache 
    </codeblock> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C0FCB407A1344527A532A1EAEF0387E4"> 
      <li id="li_8905BCF15F0F493D90B5F1135AEC149C">Visitor ID </li> 
      <li id="li_2D1FAAF35CE24CE49D1AE3F24E4A5A86">App Version </li> 
      <li id="li_A7D11680A9554414878E6CBD03B66DC4">Intent </li> 
      <li id="li_64308721D00441FBB7E6EA6EDF93C100">*blank playlist </li> 
      <li id="li_A1B2C4E27F9E4B61AAA6373DA8CEB8F2">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Play "My Heart Will Go On" by Celine Dion </p> </td> 
   <td colname="col2"> <p> "okay playing 'My Heart Will Go On' by Celine Dion" </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> 
    <codeblock>
      GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangePlaylist&amp;pageName=&nbsp;ActionPlaySong&amp;c.SongID=[012345]&nbsp;&nbsp;HTTP/1.1 
     
&nbsp;Host:&nbsp;sc.omtrdc.net 
     
&nbsp;Cache-Control:&nbsp;no-cache 
    </codeblock> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_5D782E44875144BF96877897E1180D18"> 
      <li id="li_CB5009ED407A4D4ABF3AAFE73133CC66">Visitor ID </li> 
      <li id="li_D15D65E315964E0CBF75A87CF3FCF9B5">App Version </li> 
      <li id="li_055D7621BE1D44BA8B8C50E2E45DA6DF">Intent </li> 
      <li id="li_1D52C0AB9C12483E9CD7DC216D809E44">Song ID </li> 
      <li id="li_5CFB748D02E84050AE216FDC55C680E2">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Change playlist </p> </td> 
   <td colname="col2"> <p> "okay what playlist do you want?" </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <codeblock>
      GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangePlaylist&amp;pageName=&nbsp;AskForPlaylist&nbsp;&nbsp;HTTP/1.1 
     
&nbsp;Host:&nbsp;sc.omtrdc.net 
     
&nbsp;Cache-Control:&nbsp;no-cache 
    </codeblock> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_7167AE13BBC64CC99E4A81B1FF6C9208"> 
      <li id="li_15554F7C8AC3487797A2FB65C8C1E636">Visitor ID </li> 
      <li id="li_11254FBCFA60436FB705D5FE4C313CC5">App Version </li> 
      <li id="li_4F3AE5B191DB4E73A2C08065A3D75188">Intent </li> 
      <li id="li_7F03D76A26254E65AAEB8E7D647895CA">*blank playlist </li> 
      <li id="li_DFB50E6BCEAF440D942B30A56CDD1503">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Play Usher </p> </td> 
   <td colname="col2"> <p> "okay playing Usher" </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <codeblock>
      GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=ChangePlaylist&amp;pageName=&nbsp;ActionPlayPlaylist&amp;c.Playlist=Usher&nbsp;&nbsp;HTTP/1.1 
     
&nbsp;Host:&nbsp;sc.omtrdc.net 
     
&nbsp;Cache-Control:&nbsp;no-cache 
    </codeblock> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BE5815D13CFA48408B4612D220356518"> 
      <li id="li_716EA824A56241A282FD1774A51CF52C">Visitor ID </li> 
      <li id="li_02CC3C2A66E44BB4BA865893F3206A6C">App Version </li> 
      <li id="li_558B15EC8605495B8DC01E644602FC4F">Intent </li> 
      <li id="li_21599097A3B14E368693C77CC7BA8ADD">Playlist </li> 
      <li id="li_70F4254A33704DA18D4D22028A1656E4">Response </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Turn music off </p> </td> 
   <td colname="col2"> <p> *no response, music turns off </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> 
    <codeblock>
      GET&nbsp;/b/ss/[rsid]/0?vid=[UserID]&amp;c.a.AppID=Spoofify1.0&amp;c.Intent=Off&amp;pageName=TurnsOffMusic&nbsp;&nbsp;HTTP/1.1 
     
&nbsp;Host:&nbsp;sc.omtrdc.net 
     
&nbsp;Cache-Control:&nbsp;no-cache

    </codeblock> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C623E19496DD466DA299AD610CE5ED1D"> 
      <li id="li_6A7AEF89A74C431C84D107E4F23AE223">Visitor ID </li> 
      <li id="li_B8CFF6AAB2E2476786026A98337589AF">App Version </li> 
      <li id="li_534596CB56B24B729AAA801A7B4D9D31">Intent </li> 
      <li id="li_CA3328E5FFF442BAA0F11C51DF2ED53F">Response </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

