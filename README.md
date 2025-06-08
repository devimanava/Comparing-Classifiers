# Comparing Classifiers


## Objective
The goal is to compare the performance of the classifiers (K Nearest Neighbor, Logistic Regression, Decision Trees and Support Vector Machines) using a dataset from a Portugese banking institution that has results of multiple marketing campaigns with success being if a client / contact subscribes the deposit. 

## Overview of the Approach
For this analysis, the below steps were taken::

a) Understanding the Data: The dataset used here has information about 17 marketing campaigns conducted between May 2008 and November 2010. There were phone campaigns conducted for a total of 79,354 contacts where an attractive long-term deposit with good interest rates was offered. For the whole dataset, there were 6,499 successes (8% success rate) - the dataset includes the attributes stored for each contact and a variable to indicate success. 

b) Review Features: For this, the categorical columns were reviewed using bar plots and numerical columns were reviewed using Dataframe's describe function - based on these the columns 'poutcome', 'pdays', 'previous', 'emp.var.rate', 'cons.price.idx', 'cons.conf.idx', 'euribor3m' and 'nr.employed' were not considered for mode building since they had very low variability or low influence on overall outcome

c) Feature Transformation: Categorical columns were transformed through one-hot encoding and numerical columns were transformed using StandardScaler() to prevent dominance of larger numerical features.

d) Model Evaluation: Post feature transformation, the data was split into test and training data. Logistic regression, KNN, decision tree and SVM models were then fit on the training data and validated on test data. The models were then compared based on time to train, accuracy scores, recall score and F1 scores (recall score was used since the data was imbalanced towards contacts not subscribing for deposits). 

e) Hyperparameter Tuning: GridSearchCV was used to fine tune logistic regression, KNN, decision tree - SVN model was not considered due to the compute needs. 


## Development Details
The Jupyter notebook prompt_III.ipynb has the code and execution results for each phase listed above. The data used can be viewed in the data folder


## Findings from the Exercise

a) Logistic Regression seemed to perform the best on test data based on the time taken to train, accuracy and recall scores

b) Hyperparameter tuning yielded very little improvemnts when compared to model runs using default hyperparameters

## Open Questions
a) Since the data is highly imbalanced and the cost of a false negative is high since it is important to be able to predict a successful scenario (deposit being made), should additional data preprocessing be done before model building and hyperparameter tuning to address the imbalance (e.g. oversampling / undersampling)? If so, when should it be done?

b) Hyperparamter tuning for LR, KNN and Decision Tree models did not show a significant improvement - are there any other factors other than the data imbalance that could be causing this?



