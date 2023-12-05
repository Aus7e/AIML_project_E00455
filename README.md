# AIML_project_E00455


Jan Hybl           
Alessandro Maria Austeri           
Gianmarco Mancini

# Project_1_Trains

**[Section 1] Introduction**

We were given a dataset about customers’ satisfaction of ThomasTrain company. The main goal was to predict whether a customer is satisfied (so a binary classification task), however, it might be beneficial to understand also what are the main drivers of customer satisfaction so that for example a company knows what to improve to enhance customer satisfaction.


**[Section 2] Methods**

The dataset consists of 129880 observations and 25 attributes (which are described in detail in the project assignment). Since there are only 393 missing values (0.3% of the dataset) we decided to simply drop them. After that, we checked for duplicates (not present), converted target Y/N variable into 1/0 variable so that we can see for example a correlation or mean and inspected all the numeric data, to check that all the values are in expected or reasonable ranges. We dropped useless Ticket ID column and converted Date and Time from categorical form into datetime format so that we could later try to extract useful information. After that, we plotted histograms of categorical and rating features with the proportion of satisfied customers on each category/rating which gave us valuable insights into potential predictive power of such variables. Then, we plotted pair plots of remaining numeric variables to get deeper insights into relationships of these variables. The next step was to calculate all the possible correlations to see which explanatory variables are unusually significantly correlated and also to confirm which of the features were very likely going to be able to explain whether the customer is satisfied or not. Since departure and arrival delays very extremely correlated, we dropped arrival delay, however, we thought it might be interesting to derive a new column – delay change calculated as a difference between arrival and departure delay. The next step was to check the distributions of remaining float variables and remove the most significant outliers. After that, we extracted the information about month, weekday and hour, but after plotting these variables together with the proportion of satisfied clients we did not see any useful pattern, so we dropped them. Finally, we converted categorical variables into dummy variables and were ready to start building our models.
We decided to use 2 relatively simple algorithms suitable for binary classification, a logistic regression and a decision tree, and one more complex, a random forest, to see if it improves the performance. For fitting we used a train set (75% of the dataset) and for main testing a test set (25% of the dataset). 



**[Section 3] Experimental Design**

1)	As it was already mentioned above, during EDA, we extracted information about Month, Weekday (Monday,        Tuesday,…) and Hour to see if it can help us better predict the result (for example on Mondays or            morning hours the trains tend to be more crowded which could negatively impact the customer           
    satisfaction). However, we did not find it useful since month was basically only February and a few 
    observations from March and for weekday and hour the proportion of satisfied clients on each of the 
    ‘categories’ was almost a perfect constant.
2)	Another thing that has already been mentioned – from information about arrival and departure delays we 
    derived a delay change explanatory variable. Based on the charts of this variable, it seemed to have 
    expected effect (in the area with the highest density, positive delay change descreased user 
    satisfaction rate and negative delay change increased it) and when used in the model, it was one of the 
    most important features based on the feature importance.
3)	The last thing we experimented with was the feature selection for logistic regression since it can be 
    quite sensitive to it. We tried several combinations of the model inputs and compared its confusion 
    matrix / accuracy, however, the most accurate result was the one where we used the same features as in 
    previous models.






**[Section 4] Results**

If we want to predict whether a customer will be satisfied, the most accurate model will be our random forest with the accuracy of (and other common metrics close to) 96%. However, maybe it is more useful to understand what the main drivers of the user satisfaction are so that the company knows what to focus on if they want to increase it. Among those that the company can affect (we do not assume it can significantly influence for example the delay) we can mention food and drink quality and general comfort (both legroom service as well as seat comfort). On the other hand, it would be probably just a waste of resources to try to affect for example a track location. We can see the details in the following graphs:




<img width="454" alt="image" src="https://github.com/Aus7e/AIML_project_E00455/assets/92274266/a261eb18-0829-4eaa-8213-bade6db4c735">



<img width="454" alt="image" src="https://github.com/Aus7e/AIML_project_E00455/assets/92274266/6c06f123-97af-4b12-8b09-ce78094fcad5">


**[Section 5] Conclusions**

The main findings were described in the previous section. Potential areas for improvement include mainly more robust hyperparameter tuning (if we wanted to run it for hours, it if possible we would achieve better confusion matrix) and probably also very careful feature selection in logistic regression (however, we do not have sufficient knowledge in this area). Potential follow-up is for example to dive deeper into how to increase satisfaction of particular subsets of our customers (we can see that when they travel for leisure and not for work, they are very unlikely to be satisfied, but how can we improve this – is it the same way as for the whole dataset or is there anything specific for this subset?)



