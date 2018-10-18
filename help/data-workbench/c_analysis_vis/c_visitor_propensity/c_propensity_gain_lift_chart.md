---
description: The Lift and Gain charts offer visualizations for evaluating the potential performance of a scored model to evaluate performance over defined portions of the audience.
seo-description: The Lift and Gain charts offer visualizations for evaluating the potential performance of a scored model to evaluate performance over defined portions of the audience.
seo-title: Propensity gain and lift charts
solution: Analytics
title: Propensity gain and lift charts
topic: Data workbench
uuid: 63f8e235-7821-42a7-af08-d43469ac7a10
index: y
internal: n
snippet: y
---

# Propensity gain and lift charts

The Lift and Gain charts offer visualizations for evaluating the potential performance of a scored model to evaluate performance over defined portions of the audience.

Gain and lift charts are visualizations built to evaluate the potential performance of the scored model. These charts evaluate performance over each portion of the population.

**To open a lift or gain chart**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring]. 
1. Hover over **[!UICONTROL Model Complete]** of a saved score.

![](assets/propensity_lift_gain_1.png)

**About lift and gain charts**

The Lift and Gain Charts are useful visual tools for measuring the value of a predictive model. Both charts consist of a lift curve (green) and a baseline (pink). For the **Gain Chart**, the distance between the lift curve and the baseline represents how much you can improve performance in responses (or the " gain") from using the predictive mode. The gain is realized by prioritizing and targeting the prospects (customers/visitors) who are most likely to convert, rather than marketing to customers/visitors at random. In this way, you can quantify the expected value of using the predictive model to choose which prospects to contact.

Similar to the Gain Chart, the **Lift Chart** shows how much more likely you are to receive positive responses than if you contacted prospects at random. You want the distance between the lift curve and the baseline to be as large as possible, representing larger expected gains from using the predictive model to contact customers. Mathematically, the gain and lift charts are defined as follows:

* **Gain** = (Expected Response using Predictive Model to Contact Prospects) / (Expected Response from Randomly Contacting Prospects) 
* **Lift** = (Expected Response among a Specific Group Size of Prospects identified using the Predictive Model) / (Expected Response among the same Specific Group Size of Prospects identified Randomly)

**Example of lift and gain charts**

For example, consider the example of a retailer who wants to launch an email re-marketing campaign to sell yoga pants. Historically, the analyst expects an average response rate of 20 percent based upon past email re-marketing campaigns similar to this one. While the analyst has nearly 5 million customers in its email database, the business only wants to market to those customers that are most likely to respond to the email and purchase. In this way, the company will maximize the ROI of the campaign while ensuring that they don't unnecessarily send emails to uninterested customers. Given an expected response rate of 20 percent, the marketer and analyst expect that approximately 1 million customers are likely to respond and purchase. Rather than randomly guessing which of those customers will be among the 20 percent responses, the analyst wants to be smart about predicting which of the one million prospects (among the database of 5 million customers) are most likely to respond.

Using Adobe's Audience Scoring capability, the analyst defines success as a prospect clicks on an email and purchases yoga pants (the dependent variable). After selecting the independent variables (based upon experience and knowledge gained from analyzing data correlations and audience clustering among other analyses), each prospect is scored on their likelihood of positively responding the email re-marketing campaign (clicking on the email and purchasing yoga pants). The analyst opens the resulting Gain and Lift charts based upon the predictive model.

The y-axis shows the percentage of the cumulative expected positive responses. In our example, we expect a total of 1 million positive responses. A value of 20% on the y-axis corresponds to 20% of the 1 million expected positive responses, or 200,000 positive responses. The x-axis shows the percentage of prospective customers contacted. In our example, the x-axis represents a fraction of the 5 million customers in the email database. The baseline (Pink) is the overall response rate - if you contact X% of prospects then you will receive X% of the total positive responses. Using the predictive model, the lift curve (green) shows the percentage of positive responses obtained (y-axis) by contacting a given percentage of prospects (x-axis).

The Lift chart plots the expected lift as a result of using the predictive model to determine the top one million prospects most likely to purchase yoga pants after receiving and clicking on the email. For contacting 20 percent of randomly selected prospects using no predictive model, you should expect to get 20 percent of responders. However, using the predictive model to identify the top 20 percent of prospects most likely to respond, you expect to get 50% of responders. The y-value of the lift curve at 20 percent is 50/20 = 2.5. The lift chart shows how much more likely you are to receive respondents than if you contact a random sample of prospects. For example, by contacting only 20 percent of prospects based on the predictive model you will reach 2.5 times as many respondents as compared to having not used any predictive model. 
