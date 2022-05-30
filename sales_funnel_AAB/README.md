
# Sales Funnel AAB Testing

👉 View the `notebook` **[here](https://nbviewer.org/github/shirarua/practicum-projects/blob/main/sales_funnel_AAB/sales_funnel_AAB_test.ipynb)** using **nbviewer**.


## Project description
### Objective
A food delivery app wants to understand user behavior within the sales funnel. We have run an A/A/B test to explore the effects of an app-wide font change on user behavior. Analyze the results of the A/A/B test to determine if this change will be beneficial in increasing user conversion.

### Description of data
`logs_exp.csv`: user event logs
- **EventName:** the type of action/event
- **DeviceIDHash:** unique user id
- **EventTimestamp:** the time of the event
- **ExpId:** experiment group number
    - Control groups: 246 & 247
    - Experimental group: 248

### Libraries to run the notebook locally
***Python version 3.8.8***
|Library| Version|
|---|---|
|Pandas | 1.3.5 |
|NumPy | 1.20.1 |
|SciPy | 1.6.2 |
|Sidetable | 0.9.0 |
|Matplotlib | 3.5.2 |
|Plotly.express | 5.3.1 |
|Seaborn | 0.11.2 |


## Project overview

### Prepare data
- Removed fully duplicated rows that show simultaneous repeated actions by the same user.
- Extracted date & time from the timestamp and saved them to new columns for easier analysis.

### Exploratory analysis
*Overall dataset exploration*
- Analyzed overall event frequency over time: both throughout the day and daily.
- Filtered out dates with incomplete data to focus on the true range of the experiment.
- Checked experiment groups to ensure they are similar sizes and that no users were mistakenly assigned multiple groups.

*Sales funnel analysis*
- Idenitified event types and their total frequency.
- Calculated the proportion of users who completed each action (conversion rate).
- Determined the most common order of events (discounting the optional tutorial) by ordering the first instance of each event type per user, and identifying the most common paths.
- Separately analyzed user paths of users who watched the tutorial using th esame method as above.
- Calculate overall conversion rate, as well as user retention at each stage of the event funnel.

### Analyze the results of the A/A/B test (*hypothesis testing*)
- Plotted & compared the conversion funnel of each experiment group.
- Created a hypothesis testing function to calculate the z-scores comparing the retention rate of each group at each stage of the sales funnel.
- First compared the two control groups to ensure there were no unanticipated problems with our test.
- Compared the experimental group to each control group separately.
- Compared the experimental group to the combined control groups.
- Calculated the Family-Wise Error Rate to determine if alpha values should be adjusted.

### Conclusion

No significant differences were found between the experiment group and the control groups, even without adjusting the alpha. The font change seems to have no impact on customer retention or conversion. 

The greatest loss of customers occurs immediately after accessing the main screen. 95% of customers who reach their carts go on to complete a purchase. We should focus our efforts on improving retention up until this stage, particular from the main screen to the offer screen. It is possible that watching the tutorial first may play a role in customer retention, but further experiments research is needed.
