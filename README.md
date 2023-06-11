# Credit Card Default

# Context
This was the first data science project that I did. It was done as part of an individiual assignment as part of our module BC3409 AI in Accounting and Finance. 

# Importance of Project
This project that was done is to predict whether a customer would default on their loan in the future (specifically next month) based on their personal information, and past history using a machine learning model.

This is important to the bank for 2 main reasons:

1. It helps banks to minimise their credit risk by identifying customers who are more likely to default and not grant them loans, leading to minimised monetary loss for the bank. By identifying these people, the bank could decide to avoid loaning them money altogether, or change them an increased interest rate in response to compensate for the additional risk incurred. This is proactive credit risk management, enabling the bank to intervene at the earliest opportunity so that they have more options for remedying the situation and mitigating / avoiding losses.
2. It helps the bank make better lending decisions based on multiple predictors, and is more accurate than traditional methods like looking at credit risk or income levels. A predictive model takes into consideration multiple factors like demographics, gender, employment history etc. to come to a decision based on correlations that humans cannot detect as accurately. 

# Dataset
The dataset can be found at https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset, and various other places.

# Evaluation

Overall, the results of the models used could be improved by increasing the number or predictors towards the probability of default. There are only 8 used as previously stated, namely: credit limit, sex, education, marriage, age, how long payment was made / not made in previous months, how much needed to be paid in previous months, and how much was paid in previous months. Other important predictors could be included as well, such as the customer's monthly net income, their credit score, and their current interest due. Increasing the number of predictors would help the models used to find important correlations between loan defaulting and these predictors, which would increase the accuracy of our model. However, one potential drawback of adding too many predicotrs is that the model might be overfitted since there is too much random noise. 

Another point for consideration in this dataset was that we could have used K-means clustering to identify which predictors were significant and subsequently remove the predictors were less important from our analysis. Some predictors are not immediately obvious as to how they affect loan approval, so machine learning models like K-means clustering would help discover these patterns. However, since there are very few predictors in the dataset, it was decided that clustering was not necessary and would in fact decrease the accuracy of the model. 

The last point for consideration is oversampling the minority. Since there are less customers who had defaulted on their loan payments than customers who didn't, we can consider oversampling the underrepresented class to balance the dataset, and provides the model with more examples of defaulting. However, it was decided that oversampling was not necessary in this scenario. The minority class does not sufficiently meet the criteria for oversampling since it represents 22.6% of the sample population, while the artitrary threshold we set is at 20%. Furthermore, oversampling is not representative of the entire population and does not reflect real-world scenarios, and all defaults are not necessarily similar to the few minority cases that were oversampled, which would lead to overfitting of the model. 

Models:

We could decide which model is the best through its accuracy. In ascending order, the accuracies are: Decision Tree (72.43%), Neural Network (80.07%), Random Forest (80.86%), Gradient Boosting with Hidden Layers (81.35%), Gradient Boosting (81.55%), Logistic Regression (81.62%). However, we also have to take into consideration the nature of what we are predicting. Since we are predicting whether to provide a loan, and the bank obviously does not want to lose money, the model used should favour the scenario where we do not provide someone with a loan but they would not have defaulted, versus the scenario where we do provide someone with a loan and they default i.e. we rather have false positives than false negatives. Hence, we could also look at the precision-recall diagram and roc curve to determine which model would be the best. Therefore, we could also consider using gradient boosting, since it has the greatest area under curve for ROC Curve at 76%, while having the 2nd highest accuracy overall. 

# Future Improvements

Future studies could:
1. Balance out the dataset and predictors, not limited to the "default payment next month" column. This would allow the dataset to be balanced and increase the accuracy of model.
2. Adding additional variables as previously mentioned above. 
3. If deciding to use models such as neural network, gradient boosting, random forest, include explanations and justifications for decisions made so the decision-making process would be easier to understand and explain to a layman. 
4. Consider colinearity issues / clustering and eliminate unnecessary or excess predictors where applicable. 
5. Model maintainence to ensure that performance of the model is up to baseline standard, accomodating changes in the customers profile / spending habits etc. 
6. Hyperparameter tuning to improve accuracy of models. 

# Contributions

This was an individual project. 
