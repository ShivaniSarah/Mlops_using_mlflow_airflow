# Mlops_using_mlflow_airflow

![image](https://user-images.githubusercontent.com/44539139/232208792-836692b0-0da7-4e19-867c-50848668b410.png)

The major principles of MLOps are as follows:

Scalability
Reproducibility
Automation
Collaboration
In this assignment, we will focus on reproducibility, automation and a few aspects of collaboration. Scalability falls outside the scope of this assignment. It is advisable to learn scalability as and when you get into this industry. Let’s take a look at the business context of the problem statement.

At the initial stage, customer acquisition cost is required to be high in companies. But as their businesses grow, these companies start focussing on profitability. Many companies first offer their services for free or provide offers at the initial stages but later start charging customers for these services. For example, Google Pay used to provide many offers, and Reliance Jio in India offered free mobile data services for over a year. Once these brands were established and brand awareness was generated, these businesses started growing organically. At this point, they began charging customers.

Businesses want to reduce their customer acquisition costs in the long run. There are many ways to do that. You will learn about these methods in the next segment.

In the funnel above, you can see that the reasons for the high customer acquisition cost are as follows:

Improper targeting 
High competition
Inefficient conversion
Let’s discuss how these issues can be tackled and how we, as a data science team, can help in the reduction of CodePro’s CAC.

We understood the following:

Improper targeting can be resolved by the marketing team. They can do so using better targeting strategies and using ad recommendations.
To resolve the issue of high competition, brand differentiation is required, which can be taken up by the product team.
To address inefficient conversion, the sales team must undergo upskilling and prioritise the leads generated.
The sales team must work with the data science team to figure out how to prioritise leads. The data science team must come up with lead scoring for all the leads generated.

The main objectives of lead scoring are as follows:

Remove Junk by categorising leads on the basis of propensity to purchase
Gain insights to streamline lead conversion and address improper targeting
We have chosen L2AC (Leads to Application Completion) as our business metric, as choosing L2P (Leads to Payment) will aggressively drop the leads.
A lead is generated when any person visits CodePro’s website and enters their contact details on the platform. A junk lead is generated when a person who shares their contact details has no interest in the product/service.

Having junk leads in the pipeline creates significant inefficiency in the sales process. Thus, the goal of the data science team is to build a system that categorises leads based on the likelihood of their purchasing CodePro’s course. This system will help remove the inefficiency caused by junk leads in the sales process.

We have seen that we are creating three different pipelines for our use case.

Data Pipeline
Training Pipeline
Inference Pipeline
Our system metrics for the ML model are :
AUC score >75%
Precision > 65%
Recall > 75%

Since this is the first iteration of the model we are not aiming for high performance from the model but we are aiming to get value from the model as soon as possible by deploying the model into production, and then continuously improving our model once our baseline is deployed. Thus we will not focus much on developing the best possible model but we will make do with a simple model and focus more on deploying it into production.

We will understand the pipelines in detail in the upcoming segments. Please make sure that you are following all the instructions given in the modules diligently for getting the final output. Let us understand the dataset in the next segment

Let’s recall the problem statement pitched to us by CodePro’s sales team. We had to weed out junk leads from our system. The sales executives are calling potential leads; however, several of them are turning out to be junk leads. This is leading to the wastage of the company’s time and resources. Hence, the business objective is to improve the efficiency of the sales process, i.e., to increase L2AC. Data science team discussed that we can predict the L2AC flag using the origin of the leads and how they are interacting with the platform. Let’s now take a look at the data set that we received from the sales team. 

Understanding the Data

To classify any lead, we will require two types of information about it:

Origin of the lead: To better predict the likelihood of a lead purchasing a course, we need some information on the origin of the lead. The columns from ‘city_mapped’ to ‘reffered_leads’ contain the information about the origin of the lead.
Interaction of the lead with the website/platform: We also require information about how the lead interacted with the platform. The columns from ‘1_on_1_industry_mentorship’ to ‘whatsapp_chat_click’ store the information about a lead’s interaction with the platform.

Origin of a Lead

To understand the origin of a lead, we have the following information:

created_data: This is the timestamp identifying when a lead was created.

city_mapped: This is the city where a lead was generated.

first_platform_c: This is the place that leads users to the source - mobile web, desktop web, Android app, etc.

first_utm_medium_c: Mediums are broad buckets of categories that describe the type of traffic being driven to your website. For example, ‘organic’ 
is a medium because it encompasses traffic coming from search engines such as Google. ‘Referral’, ‘social’ and ‘paid’ are other examples of mediums.

first_utm_source_c: The source is where your website’s traffic comes from (individual websites, Google, Facebook, etc.). For example, think of a 
journey - the source would be where you came from, and the medium would be the mode of transport.

total_leads_dropped: This refers to the count of leads accessed by the user. For example, a user might browse through multiple Python courses while looking for the best course based on their requirements.

interaction type columns: These capture the type of interaction a user had with the CodePro website. For example, the user might look at payment options, syllabus, placement records, etc.

App_complete_flag: this is the column we are trying to predict. We are trying to understand whether a user will fill the application or not based on the information in the previous columns.

Referred_lead: This indicates whether a lead was referred or not.

Starter Code:

https://drive.google.com/drive/folders/1_8i1iQPdJF3A-IDAwGuUCejOW60lNocl
