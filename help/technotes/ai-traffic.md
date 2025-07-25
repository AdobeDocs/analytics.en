---
description: Understand how to report on traffic from AI chatbots
title: Analyze traffic from AI chatbots
feature: Metrics, Data Configuration and Collection
---
# Analyze traffic from AI chatbots

Adobe Analytics provides tools for analyzing AI traffic on your website.

When analyzing AI traffic, you first need to understand the types of AI traffic that can occur and which types generate hits. Then, you can analyze the traffic in Analysis Workspace.

## Understand AI traffic

### Understand the types of AI traffic

AI traffic on your website can occur in any of the following circumstances:

* **During pretraining**: Occurs infrequently, when content from your website is scraped and ingested into the AI training data. 

* **When responding to on-demand prompts**: Occurs the moment the user prompts AI with a question and the AI chatbot responds. The AI chatbot performs a web search and content from your website is included in the response. (This type of interactions is sometimes referred to as Retrieval-Augmented Generation (RAG).)

  Some AI chatbot responses include links to the source material on your site and some do not. 

* **When executing agentic workflows**: Occurs any time an AI agent visits your website when clicking through a series of web pages in a browser in order to respond to a user request. In this case, the AI is acting as an agent for the user who made the request. 

### Understand when hits are generated for AI traffic

A hit is generated on a webpage when JavaScript is executed on the page. Depending on the type of AI traffic that is occurring on your site, JavaScript might or might not be executed.

| AI traffic type | Generates hits | Considerations |
|---------|----------|---------|
| **Pretraining** | Yes | Hits are generated during pretraining when the content from your website is ingested into the AI. However, pretraining occurs infrequently, and content that is included in an AI's pretraining can be reused again and again in future responses without generating futher hits on your website. <p>In other words, a single hit that occurs during an AI's pretraining can be reused again and again for multiple on-demand responses without generating additional hits on your website.</p><p>For information about how to analyze this type of AI traffic in Analysis Workspace, see [Analyze AI traffic using bot detection](#analyze-ai-traffic-using-bot-detection).</p> |
| **On-demand prompts** | No | The AI response does not generate any hits because the response uses a combination of:<ul><li>Pretrained data <br/>Information is already included in the AI's pretrained knowledge, so the AI does not execute JavaScript on pages.</li><li>On-demand web search <br/>Fetches only the raw HTML of the web page during the web search, so the AI does not execute JavaScript on pages.</li></ul> |
| **Source material links in AI responses** | Yes | Hits are generated when a user clicks the link to source material that is included in the AI response. A hit is not generated if a link is included in the response and the link is not clicked by the user. <p>Some AI chatbot responses include links to the source material and some do not. </p><p>For information about how to analyze this type of AI traffic in Analysis Workspace, see [Analyze AI traffic by Referrer type](#analyze-ai-traffic-by-referrer-type).</p> |
| **Agentic workflows** | Yes | Hits are generated on each page as the AI agent clicks through the workflow on behalf of the user. <p>For information about how to analyze this type of AI traffic in Analysis Workspace, see [Analyze AI traffic by Referrer type](#analyze-ai-traffic-by-referrer-type).</p> |

## Analyze AI traffic in Analysis Workspace

### Analyze AI traffic by Referrer type

You can use the Referrer type dimension in Analysis Workspace to analyze the following types of AI traffic:

* Source material links in AI responses

* Agentic workflows

The Referrer type dimension includes the [AI chatbots dimension item](/help/components/dimensions/referrer-type.md#ai-chatbots). This dimension item includes a predefined list of AI chatbots. 

For more information, see [Referrer type](/help/components/dimensions/referrer-type.md).

### Analyze AI traffic using bot detection

You can use bot detection in Analysis Workspace to analyze AI traffic that comes from pretraining.

