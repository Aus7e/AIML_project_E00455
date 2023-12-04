# AIML_project_E00455


Jan Hybl
Alessandro Maria Austeri
Gianmarco Mancini

# Project_1_Trains

# INTRODUCTION

First of all, we have checked all the null value in our set. By using df.isnull().sum()) we can check for each column how many isnull value we have. 
We can see that on the column "Arrival Delay In Minutes", we have 239 not valid values, that are the 0.3% of the values, we should decide if we have to drop the column or to ignore that values.

Then we have to analyze which column are useless for modeling, we can say that the column "Ticket ID" is useless, so we can drop it.

We start our EDA  computing some plots for each category, (hist plot,  pair plot, correlation matrix, box plot).

After this, we should scale integers and floats.
