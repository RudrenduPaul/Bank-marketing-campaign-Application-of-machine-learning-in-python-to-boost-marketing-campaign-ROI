# Python - Bank Marketing campaign - machine learning to boost marketing campaign ROI 

Please click on the Bank Marketing Campaign - Paul - Final.ipynb file above to see the detailed python code and its interpretation

Bank Marketing Campaign (aplication of analytics and machine Learning models to improve marketing campaign ROI

This is a real data set from the marketing campaign of a bank with over 40000+ people on the list

Data source: https://archive.ics.uci.edu/ml/datasets/bank+marketing

Average response rate of people on list is 11% and hence, marketing to each person on the list incurs a loss of $ 34,000 with a ROI of negative 44 %.

This machine learning model identifies the top customer segments with high probability of conversion of around 40% (4X the average) by rank scoring the people on list (targetted list) and provides a positive ROI of 79 % on a targetted list of people.

### Snapshot of analysis:

Details are in the Bank Marketing Campaign - Paul - Final.ipynb file

### Average response rate: 
Overall distribution of campaign reponse in the original datset:

![overall_repsonse](https://user-images.githubusercontent.com/38769913/53281021-19897300-36f0-11e9-877d-8c1acc627b98.png)

## Data Exploration of variables in dataset: 

### Age:

![age_distribution](https://user-images.githubusercontent.com/38769913/53280932-7d12a100-36ee-11e9-9be8-34b5656b9967.png)

### Statistical test on Age: 

#### Average of mean age of people who responed "Yes" vs those who responded "No"

The 95% confidence interval of the difference of means is [ 0.591 ,  1.413 ]. Hence, the difference of the mean of age is statistically significant at 95% confidence interval because the 95% confidence interval does not include 0.

### Job:

![job](https://user-images.githubusercontent.com/38769913/53280935-8996f980-36ee-11e9-8b08-cfa7d173249f.png)

### Statistical test on Job: 

#### Chi square test of Job between 2 groups of people who responed "Yes" vs those who responded "No"

p value of chi-square test:  4.232405679993378e-200

The chi square test shows that job is statistically significant at 95% confidence interval is whether people responded yes or no to the marketing campaign as the p value of the chi square is less than 5 %.
From the chart shown above for the proportion of each job type in each groups, for people with the following job types had a higher % of responding "yes" than those who responded "no",

Admin jobs,
Retired
Students.

#### Education:

![education](https://user-images.githubusercontent.com/38769913/53280936-91569e00-36ee-11e9-9a41-a7a80e3c07d9.png)

### Statistical test on Education: 

#### Chi square test of Education level between 2 groups of people who responed "Yes" vs those who responded "No"

p value of chi-square test:  2.2494049169426562e-35

#### Analysis:
The chi square test reveals that education level is statistically significant at 95% confidence interval as p value is less than 5 %. From the chart above, those who responded "yes" had a much higher proportion of people with higher education (university.degree, high.school & professional.course) than those who responded "no".


### Models applied:

1) Logistic regression model (with L1 regularization)
2) Naive bayes classifier model
3) KNN classifier model
4) Decision tree classifier model
5) Random forest classifier model

Logictic Regression with L1 regularization: 

![auc_logistic__l1_reg](https://user-images.githubusercontent.com/38769913/53280939-9ae00600-36ee-11e9-92ae-a8fa5dd1e27c.png)

AUC score for logistic regression with L1 regularization: 

Random Forest:

![auc_random_forest](https://user-images.githubusercontent.com/38769913/53280959-a253df00-36ef-11e9-8040-a871d13ff3dc.png)

AUC score for random forest: 

Top 10 most importamt variables based on random forest model:
  1. age
  2. poutcome_success
  3. housing_yes
  4. housing_no
  5. previous
  6. job_admin.
  7. marital_married
  8. education_university.degree
  9. education_high.school
  10. marital_single

### Model Comparison: 

![model_comparison](https://user-images.githubusercontent.com/38769913/53280966-1346c700-36ef-11e9-8070-abbd0aeac46a.png)


### Model selection: 

Linear logistic regression gives the best results, based on the highest AUC score on test data set.

#### Lift Chart

How well my model is performing compared to campaigning to everyone on the list using the best model? 

Plot shows how much improvement the rank scored response is performing decile of customers targetted 

![lift chart - test set](https://user-images.githubusercontent.com/38769913/53280961-fc07d980-36ee-11e9-86fb-270d98909e68.png)


## Business Application

### Case I: Campaign by mailing everyone on list

#### Baseline performance

Mailing to everyone in list without using model

Average response rate from customers in test set list is 10.93 %

Total customers in test set list = 7,649

Expected rev from customers for every positive response is $ 10

Cost of each mailing is $ 2

#### Mailing to everyone in list

Total size of test set: 7649

Average response rate of people in test set: 10.93 %

Total campaign profit: $ -6938

ROI: -45 %

Marketing to every person on the list results in a loss of $ 6,938 and a ROI of negative 45 %

### Case II: Campaign based on model

#### Model performance

Mailing only to people in target list:

Average response rate in the top customer segment is 35.8 % (Applying elbow method on graph shown above)

Total customers in list = 1500 (Obtained from graph shown above corresponding to 36% response rate)

Expected revenue from customers for every positive response is $ 10

Cost of each mailing is $ 2

#### Marketing only to targeted list of people suggested by model:

Total campaign profit: $ 2374.0

ROI %: 79.0

Marketing to people on targetted list results in a profit of $ 2,374 and improves campaign ROI to 79 %.

Marketing to new list of people with high probability of conversion identified by the machine learning model, improves response rate to 36 % (best model), 3.6 X the overall average response rate of 11 % (baseline) and improves ROI from -45 % (baseline) to 79 % (best model).
