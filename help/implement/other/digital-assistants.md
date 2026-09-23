---
title: Implement Analytics for Digital Assistants
description: Implement Adobe Analytics on Digital Assistants, such as Amazon Alexa or Google Home.
feature: Implementation Basics
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
role: Developer
TQID: 'https://experienceleague.adobe.com/QKlchx0r3ZDourRQaQAJaMn9Fh3bXiEWHprCkLVALsk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
---
# Implement Analytics for digital assistants

With advances in cloud computing, machine learning, and natural language processing, digital assistants are part of everyday life. Consumers talk to their devices and expect human-like responses, and brands can present their services through these same experiences. For example, consumers can ask:

* "Alexa, ask my car when it needs an oil change."
* "Hey Google, what is the balance of my checking account?"
* "Siri, send John $20 for dinner last night from my banking app."

This page provides an overview of how to use Adobe Analytics to measure and optimize these types of experiences.

## Digital experience architecture overview

![Digital Assistant Workflow](assets/Digital-Assitants.png)

Most digital assistants follow a similar high-level architecture:

1. **Device**: A device (such as a smart speaker or a phone) with a microphone that lets the user ask a question.
1. **Digital assistant**: The service that powers the assistant. It converts speech into machine-understandable intents and parses the details of the request. Once the intent is understood, the assistant passes the intent and details to the app that handles the request.
1. **"App"**: An app on the phone or a voice app that responds to the request. It responds to the digital assistant, which then responds to the user.

## How data is sent to Adobe Analytics

A digital assistant app typically runs on a server or platform that has no Adobe client-side library (AppMeasurement or the Web SDK). Send hits **server-side using the [Data Insertion API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)**. Each interaction you want to measure becomes a Data Insertion API request whose query string (or XML body) carries the variables described on this page — most often [context data variables](/help/implement/vars/page-vars/contextdata.md) that you map to eVars, props, and events with [processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md).

This page focuses on *what* to measure and how to model it in Analytics. For the endpoint, the query-string and XML encodings, required components, and response types, see the [Data Insertion API documentation](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/). Each variable named below maps to a query-string parameter and XML tag in the [variable reference](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference).

## Where to implement Analytics

One of the best places to implement Analytics is in the app, which receives the intent and details from the digital assistant and determines how to respond. There are two moments during a request that are helpful to send data to Adobe Analytics:

1. When the request is sent to your app.
1. After the response is returned from the app.

If you are interested in recording what happened for future optimization, send the hit after the response has been returned — you then have the full context of the request and how the system responded.

## What to measure

### New installs

For assistants that notify you when someone installs the skill (especially where authentication is involved), send an install event by setting the context data variable `a.InstallEvent=1`, along with `a.InstallDate` and the app ID (`a.AppID`). This is not available on every platform, but is useful for retention analysis when present.

### Multiple assistants or apps

Organizations often build apps for multiple platforms. Include an app ID on every request in the `a.AppID` context data variable, using the format `[AppName] [BundleVersion]` (for example, `Spoofify 1.0`). Add a platform or OS context data variable (such as `OSType`) so you can distinguish Alexa, Google Assistant, and other platforms in reporting.

### Visitor identification

Adobe Analytics uses the [Adobe Visitor ID Service](https://experienceleague.adobe.com/en/docs/id-service/using/home) to tie interactions over time to the same person. Most digital assistants return a `userID` that you can use as a unique identifier — pass it as the visitor ID override (`vid`). Some platforms return an identifier longer than the 100 characters allowed; in these cases, hash it to a fixed-length value with a standard algorithm such as MD5 or SHA-1.

Using the Visitor ID Service provides the most value when you map ECIDs across devices (for example, web to digital assistant). If your app is a mobile app, use the Experience Platform Mobile SDK and send the user ID with the `setCustomerID` method. If your app is a service, use the user ID provided by the service as the visitor ID and also set it with `setCustomerID`. For how to set identifiers on a server-side request, see [Visitor identification using the Data Insertion API](../id/data-insertion.md).

### Sessions

Because digital assistants are conversational, they often have the concept of a session (a multi-turn exchange). When a new session starts, Adobe recommends two things:

1. **Reach out to Audience Manager** to get the segments the user belongs to, so you can customize the response.
1. **Send a launch event** with the first response by setting the context data variable `a.LaunchEvent=1`.

### Intents

Each assistant detects intents and passes them to the app. An intent is a succinct representation of the request — for example, "Siri, send John $20 for dinner last night from my banking app" might resolve to the intent *sendMoney*. Send each intent into a context data variable that you map to an eVar so you can run pathing reports across intents. Make sure your app handles requests without an intent as well; Adobe recommends sending `No Intent Specified` rather than omitting the variable.

### Parameters, slots, and entities

In addition to the intent, assistants often provide key/value details of the request (called slots, entities, or parameters). For "Siri, send John $20 for dinner last night," the parameters might be:

* Who = John
* Amount = 20
* Why = Dinner

There is typically a finite set of these per app. Send them into context data variables and map each to an eVar.

### Error states

Sometimes the assistant passes inputs your app cannot handle (for example, "Siri, send John 20 bags of coal from my banking app"). When this happens, have your app ask for clarification and send data indicating an error state — set `a.Error=1` along with an eVar that specifies the error type. Include both errors where the inputs are invalid and errors where the app itself had a problem.

### Device capabilities

While most platforms do not expose the exact device, they do expose its capabilities (such as Audio, Screen, or Video), which define the content types you can use. When measuring device capabilities, concatenate them in alphabetical order with leading and trailing colons — for example, `":Audio:Camera:Screen:Video:"` — so that you can build segments such as "all hits with `:Audio:` capabilities."

* [Amazon Alexa interface reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)
* [Google Assistant surface capabilities](https://developers.google.com/actions/assistant/surface-capabilities)

## Example request

The following Data Insertion API GET request records a *SendPayment* intent for a banking app, setting the app ID, a launch event, the intent, and slot values as context data:

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo%201.0&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&pageName=SendPayment HTTP/1.1
Host: example.data.adobedc.net
```

For the full request format, endpoints, and response types, see the [Data Insertion API documentation](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/request).

## Example measurement model

The following table shows how common actions in a music app map to Analytics variables. Set these as context data variables on each Data Insertion API request, then map them to eVars and events with processing rules.

| Person action | Intent/event | Context data to set |
| --- | --- | --- |
| Install the app | Install | `a.InstallEvent=1`, `a.InstallDate`, `a.AppID`, `OSType` |
| Launch the app | Launch | `a.LaunchEvent=1`, `a.AppID`, `Intent=Play` |
| Ask to change the song | ChangeSong | `a.AppID`, `Intent=ChangeSong` |
| Play a specific song | ChangeSong | `a.AppID`, `Intent=ChangeSong`, `SongID` |
| Change the playlist | ChangePlaylist | `a.AppID`, `Intent=ChangePlaylist`, `Playlist` |
| Encounter an invalid input | (error) | `a.Error=1`, `ErrorName` |
