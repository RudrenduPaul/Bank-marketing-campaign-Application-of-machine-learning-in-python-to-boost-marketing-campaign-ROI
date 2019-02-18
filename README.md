# Marketing campaign using machine learning techniques to boost marketing campaign ROI using python 

(Please click on the file above named; Bank Marketing Campaign - Paul.ipynb to see the detailed application of analytics and its interpretation)

Analytics based marketing campaign for improving ROI

This is a real data set from the marketing campaign of a bank with over 40000+ people on the list

Data source: https://archive.ics.uci.edu/ml/datasets/bank+marketing

Average response rate of people on list is 11% and hence, marketing to each person on the list incurs a loss of $ 34,000 with a ROI of negative 44 %

This machine learning model identifies the top customer segments with high probability of conversion of around 40% (4X the average) and provides a positive ROI of 79 % on a targetted list of people.

### Snapshot of analysis: ()
Details are in the Bank Marketing Campaign - Paul.ipynb file

Overall distribution in the original datset:

![image](https://user-images.githubusercontent.com/38769913/51408071-9773c080-1b2b-11e9-91a2-5605f9b51bf8.png)

Some data exploration:

### Response rate based on months when customers were contacted:  

![image](https://user-images.githubusercontent.com/38769913/51408163-ddc91f80-1b2b-11e9-81c0-c10b67bb51d8.png)

### Duration of phone call

![image](https://user-images.githubusercontent.com/38769913/51408252-1537cc00-1b2c-11e9-9596-1f63c21ec98f.png)

On average default rate was lower among people who responded positively, note the long tail in "default (no)".



### Feature Engineering (to reduce computation power and time)

Selecting the top 10 principal components: % of variation explained by the top 10 principal components: 85.0

Variation explained by the top 10 principal components: By applying principal component analysis, I have reduced the number of variables from 53 to 10 which explain 85 % of variation in the dataset.

### Models applied:

1) Linear logistic regression model
2) Naive bayes classifier model
3) KNN classifier model
4) Decision tree classifier model
5) Random forest classifier model

### Model selection: 

Linear logistic regression gives the best results, based on the AUC score on test data.

### Best Model

#### Lift
How well my model is performing compared to campaigning to everyone on the list using the best model? 

Plot shows how much improvement the rank scored response is performing decile of customers targetted 

![image](https://user-images.githubusercontent.com/38769913/51408653-7c09b500-1b2d-11e9-849c-d33d9a2ff60c.png)

## Business Application

### Case I: Campaign by mailing everyone on list

Mailing everyone in list without using model
Average response rate from customers to mails is 11.1 %
Total customers in list = 38245 (after data cleaning)

Expected rev from customers for every positive response is $ 10
Cost of each mailing is $ 3

#### Mailing to everyone in list
Total campaign profit: $ -36657
ROI: -44 %
Marketing to every person on the list results in a loss of $ 34,000 with a ROI of negative 44 %

### Case II: Campaign based on model

Mailing only to people in target list,
Average response rate in the top customer segment is 35.8 % (Applying elbow method on graph shown above)
Total customers in list = 1500 (Obtained from graph shown above corresponding to 49% response rate)

Expected revenue from customers for every positive response is $ 10
Cost of each mailing is $ 3

#### Mailing to only targeted list of people suggested by model:
Total campaign profit: $ 2,369.0
ROI %: 79
Marketing to people on targetted list results in a profit of $ 2,369 with a ROI of 140 %.

Using the model for campaiging improves the campaign ROI to 79 % from -44 % (baseline).

Marketing to new list of people with high probability of conversion identified by the machine learning model, improves response rate to 40 % (best model), 4X the overall average response rate of 11 % (baseline) and improves ROI from -44 % (baseline) to 79 % (best model).
