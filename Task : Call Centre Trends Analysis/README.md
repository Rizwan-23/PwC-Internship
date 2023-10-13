<H1> Call Centre Analysis

  
![Dashboard-1](https://github.com/Rizwan-23/PwC-Internship/assets/125081051/e188b992-792f-4823-a084-7b845517fd8e)





## Table of contents
- [Problem Statement](#problem-statement)
- [Data Preparation](#data-preparation)
- [Data Modeling](#data-modeling)
- [Data Visualization](#data-visualization)
- [Analysis and Insights](#analysis-and-insights)


# Problem Statement

- **Problem:** The manager at PhoneNow (a big telecom company) is seeking transparency and insight into the Call Center dataset to gain an accurate overview of long-term customer and agent behavior trends.
- **Objective:** The purpose of this analysis is to create a dashboard in Power BI for Call Center Manager that reflects all relevant Key Performance Indicators (KPIs) and metrics to:
    - Self-exploratory call trends
    - Overview of the agent’s performance and behaviors
    - Overview the customer satisfaction
    - Contain many metrics and plots related to a single area of business for discussing with higher managers and generating further analysis.
    - Allows for minimal interaction
- **Possible KPIs** include (but are not limited to):
    - Overall customer satisfaction
    - Overall calls answered/abandoned
    - Calls by time
    - Average speed of answer
    - Agents performance quadrant -> average handle time(talk duration) vs calls answered

# Data Sourcing

The Dataset used for this analysis was provided by [Pwc Switzerland](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and available here: [Call Center Dataset](https://github.com/calmk/PWC-Virtual-Case-Experience/blob/main/Task%202%3A%20Call%20Center%20Dashboard/01%20Call-Center-Dataset.xlsx)
# Data Preparation

The dataset was loaded into Microsoft Power BI Desktop for transformation in Power Query and modeling.

### Metadata

The tabulation below shows the metadata of `Call Center` dataset:

| File name |01 Call-Center-Dataset  |
| --- | --- |
| Format | .xlsx |
| Size | 249KB |
| Fields | 10 |
| Entities | 5000 |
| Time | January 1, 2021 - March 31, 2021 |

The tabulation below shows the `Call Center` table with its fields names and their description:

| Field Name | Description | Data Type |
| --- | --- | --- |
| Call Id | Represents every unique observation in the dataset | Text  |
| Agent | Describes the name of the agent | Text |
| Date | Describes the date of the call | Date |
| Time | Represents the time of the call | Date/Time |
| Topic | Describes the topic of the caller | Text |
| Answered (Y/N) | Describes if the call was answered or not | Text |
| Resolved | Describes if the problem was Resolved or not | Text |
| Speed of answer in seconds | Represents the speed of answer in seconds | Decimal number |
| AvgTalkDuration | Represents the average talk duration of a call | Time |
| Satisfaction rating | Represents the satisfaction rating of the agent during the call | Decimal number |

### Data Cleaning

Data Cleaning for the dataset was done in Power Query as follows:

- Each of the columns in the table was validated to have the correct data type


### Data Transformation

To ensure the comprehensive satisfaction of customers, an additional column named `Satisfaction Likert` was created for referencing using the M-formula: 

`Table.AddColumn(#"Added Custom", "Satisfaction Likert", each if [Satisfaction rating] = 1 then "Terrible" else if [Satisfaction rating] = 2 then "Unhappy" else if [Satisfaction rating] = 3 then "Neutral" else if [Satisfaction rating] = 4 then "Happy" else "Delighted")`

Here is a breakdown of what the formula does:

For the dataset, we want to transform the satisfaction rating from number to text based on the Likert scale with the condition if `Satisfaction rating = 1`, it will display the rating as `“Terrible”`, respectively for each value of `Satisfaction rating` .

# Data Modeling

After the dataset was cleaned and transformed, it was ready to be modeled, but the dataset just included one table, so the Data Modeling is nothing much to modify

# Data Visualization

![Dashboard-2](https://github.com/Rizwan-23/PwC-Internship/assets/125081051/2df3feb1-4ed7-4744-876f-e8e75c8da821)



Data visualization for the datasets was done in Microsoft Power BI Desktop 

### Dashboard type

Overview and Agent Analysis: **Team lead & Manager** (non-technical users)

### Key Performance Indicators and Metrics:

**About Calls and Agents:** 

- Overall calls answered/abandoned
- Calls received by time, day 
- Average speed of answer, handle duration
- Resolved rate by Agents, Topics
- Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

**About Customer satisfaction:**

- Overall customer satisfaction
- Customer satisfaction distribution by Agents, Topics
  


# Analysis and Insights

********************About Call trends:********************

- Customers tend to call more between 4:00 pm - 5:00 pm at 575 calls received with an abandoned rate is 18.45% (approximately to the average abandoned rate).
- Customers have more problems with Streaming service.

********************About performance of agents:********************

- The agent who satisfies customers most is Martha with a 42.48% of “Happy” and "Delighted" rating.
- The agent who has the highest resolved rate is Dan and he is effective with solving problems related to “Streaming” and “Technical Support”.

********************About customer satisfaction:********************

- The average customer satisfaction is at an acceptable rate with 40.46%, mainly comes from “Happy” (58.23%)
- The correlation between call answered and call resolved is strongly positive which resulted in a increase in the customer satisfaction rate
 ### Thank You!
