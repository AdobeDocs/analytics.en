---
description: After you have made all the necessary Web site updates, you can use a network traffic viewer, such as Charles*, Chrome Developer Tools, or Firebug*, to confirm DFA is communicating with Adobe collection servers.
keywords: DFA
seo-description: After you have made all the necessary Web site updates, you can use a network traffic viewer, such as Charles*, Chrome Developer Tools, or Firebug*, to confirm DFA is communicating with Adobe collection servers.
seo-title: Confirming a Successful DFA Integration
solution: Analytics
title: Confirming a Successful DFA Integration
topic: Data connectors
uuid: d658cd7c-6377-439a-850c-ecea8c41f970
index: y
internal: n
snippet: y
---

# Confirming a Successful DFA Integration{#confirming-a-successful-dfa-integration}

After you have made all the necessary Web site updates, you can use a network traffic viewer, such as Charles*, Chrome Developer Tools, or Firebug*, to confirm DFA is communicating with Adobe collection servers.

After you have deployed the DFA-enabled `s_code.js` file, use the network traffic viewer to view the requests between DFA and Adobe data collection servers, looking for the following:

* A request to DFA's `fls.doubleclick.net/json` service. This service can respond differently depending on the version of DFA you are using. With the DFA Integration version 1.5:

    * An HTTP 302 redirect to [!DNL ad.doubleclick.net]. This will send a Location: tag in the response which contains information about the ad visitor. 
    * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. This service translates the information about the ad visitor into JSON (JavaScript Object Notati on) encoded string. This data is returned with a 200 OK HTTP response.

* With DFA Integration version 2.0 (Advanced Ad Serving enabled):

    * [!DNL fls.doubleclick.net] will directly respond with a 200 OK.

In either case, a successful request will result in a request to the Adobe data collection servers that contains the parameter vX, where X is your View-Through eVar number. This parameter value takes the form: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. This string contains data about the last click and the last impression for the current visitor. 
