# Membership Churn Predictions

Click **[here](https://github.com/shirarua/practicum-projects/blob/main/churn_predictions/gym_churn_predictions.ipynb)** to view this notebook directly in GitHub. Or locate the file `gym_churn_predictions.ipynb` directly in the churn_predictions folder.

If running the notebook locally, please refer to the library versions listed in the description below.

## Project Description
### Objective
Model Fitness wants to understand which factors have the strongest impact on churn to assist in developing a more effective customer retention stratey.

Using data on existing customers (both active and inactive), explore several features to create a model to predict the probability of customer churn. Cluster customers into groups to further understanding of customer types and the features that define them. Our aim is to use this information to help reduce churn in the future.

### Data Description
 **`gym_churn_us`**: member data
- **Churn:** has the member left as of the current month
- **gender:** customer's gender
- **Near_Location:** whether the member lives/works in the neighborhood where the gym is located
- **Partner:** whether the user is an employee of a partner company (discounted membership)
- **Promo_friends:** whether the user originally signed up through a "bring a friend" offer, using another member's promo code upon signing up
- **Phone:** whether the user provided their phone number
- **Age:** member's age in years
- **Lifetime:** number of months since the customer's first visit
- **Contract_period:** length of the contract; 1 month, 3 months, 6 months, or 12 months
- **Month_to_end_contract:** the months remaining until the current contract expires
- **Group_visits:** whether the user takes part in group sessions
- **Avg_class_frequency_total:** average number of weekly visits over the *customer's lifetime*
- **Avg_class_frequency_current_month:** average number of weekly visits over the *preceding month*
- **Avg_additional_charges_total:** the total amount of money spent on other gym services (cafe, athletic goods, cosmetics, massages, etc.)

### Libraries used
Python 3.8.8
- pandas 1.3.5
- numpy 1.20.1
- math
- scipy 1.6.2: .stats, .cluster.hierarchy 
- sidetable 0.9.0 
- matplotlib.pyplot 3.5.2 
- plotly.express 5.3.1 
- seaborn 0.11.2 
- sklearn 0.24.1: .model_selection, .preprocessing, .linear_model, .ensemble , .metrics, .cluster 

## Summary
### Methodology
*Data did not require cleaning*
#### Exploratory analysis
- Explored & visulized distributions and mean values of all features in both active & inactive members.
- Calculated relationships between features.
- Determined which features to remove from the predictive model to avoid overfitting by identifying features that are overly similar.
#### Predictive modelling
- Trained data on both a logistic regression model and a random forest classifier.
- Compared the accuracy, precision, and recall of each model.
- Visualized feature importances to better understand which features have the strongest impact on churn.
#### Member clustering
- Built a dendrogram ousing linkage() function to build a matrix of distances based on a standardized feature matrix.
- Employed KMeans clustering to cluster members according to their features.
- Compared feature values of each cluster to better understand member behavior.

### Conclusions

Convenience, benefits, and social engagment all play large roles in retaining customers. 

Recommended strategies for marketing & maintaining user engagement:

- Limit marketing to individuals & businesses nearby.
- Increase partner programs with businesses nearby
- Continue encouraging members to bring in friends with incentives
- Promote group classes
- Engage with & incentivize members who have had a noticeable drop in class attendance
