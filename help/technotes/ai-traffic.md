---
description: Understand how to report on traffic from AI chatbots
title: Analyze traffic from AI chatbots
feature: Metrics, Data Configuration and Collection
---
# Analyze traffic from AI chatbots

Adobe Analytics provides tools for analyzing AI traffic to your website.


## Understand AI traffic

### Understand the types of AI traffic

AI traffic on your website can occur in any of the following circumstances:

* **During pretraining**: Occurs infrequently, when content from your website is scraped and ingested into the AI training data. 

* **When responding to individual prompts**: Occurs any time a user prompts AI with a question and the AI chatbot response includes content from your website. (This type of interactions is sometimes referred to as Retrieval-Augmented Generation (RAG).)

  Some AI chatbot responses include links to the source material on your site and some do not. 

* **When executing agentic workflows**: Occurs any time an AI agent visits your website when clicking through a series of web pages in a browser in order to respond to a user request. 

### Understand when hits are generated

| AI traffic type | Generates hits | Considerations |
|---------|----------|---------|
| **Pretraining** | Yes | Hits are generated during pretraining when the content from your website is ingested into the AI, but pretraining occurs infrequently and can be reused again and again without generating futher hits. |
| **Individual prompts** | No | Hits are generated only when the response includes a link to your website and a user clicks the link.  |
| **Agentic workflows** | Yes | Hits are generated on each page as the AI agent clicks through the workflow.  |

## Analyze AI traffic by Referrer type

For more information, see [Referrer type](/help/components/dimensions/referrer-type.md).


## Analyze AI traffic 



When is a hit recorded in Adobe Analytics for AI traffic?

When your website is linked as a source in an AI chatbot response and a user clicks the link. 

A hit is not recorded when content from your website is used to form an AI response

Is pretraining captured?

RAG hits

AI agents that browse websites on behalf of people

