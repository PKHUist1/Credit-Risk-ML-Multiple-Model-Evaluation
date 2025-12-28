# Credit-Risk-ML-Multiple-Model-Evaluation
## Project Overview
This project explores the use of machine learning for credit risk modelling
using a synthetically generated dataset designed to align with real world credit application data.

Multiple classification models were evaluated across the full machine learning
lifecycle. Model evaluation was multi-faceted, with assesment not just examining evaluation metrics but also how applicable each model would be in the context of real world credit risk modelling.  
## Business Context
Within any industry that offers credit related products, machine learning models are typically leveraged to support approval or rejection of applications. Although not the only tool used, machine learning models often reperesent a core component of assesing risk in the presence of customer attributes; ultimately indicating an approval decision. As a
result, model interpretability and stability are critical considerations
alongside predictive performance. 

This project focuses on:

Evaluating models using metrics suitable for imbalanced classification

Understanding which features drive predictions

Assessing model behaviour under realistic assumptions
## Dataset
The dataset used in this project is synthetically generated to avoid privacy
concerns while maintaining realistic feature relationships.

Features include:

Credit score

Debt-to-income ratio

Employment history

Credit history indicators

Prior default and delinquency signals
## Modelling Approach

The following models were evaluated using stratified cross-validation:

Logistic Regression

k-Nearest Neighbours

Random Forest

XGBoost

All models were implemented using sklearn Pipelines to ensure consistent
preprocessing and to prevent data leakage. Class imbalance was addressed using
SMOTE applied within training folds only.
## Model Evaluation

Models were evaluated using multiple metrics to reflect the imbalanced nature
of the target variable, including:

Accuracy

Precision

Recall

F1-score

ROC-AUC

XGBoost demonstrated the strongest overall performance and was selected for
further analysis.
## Model Interpretability

To understand model behaviour, two complementary interpretability techniques
were used:

Native XGBoost feature importance (gain-based) to assess how features
contribute to reducing model error

Permutation feature importance to evaluate the impact of each feature on
predictive performance when its information is disrupted

Both tuned and untuned XGBoost models were analysed. Despite differnt levels of variance in both feature and permutation importance across both models, the overall feature rankings remained the same. This indicates stability within both the models utilised and also the underlying data. 
## Key Findings

Credit score and debt-to-income ratio are the most predominate features for predicting credit risk across models

Historical credit indicators provide additional predictive value, but in some cases minimaly. 

Hyperparameter tuning altered how features were utilised but did not
materially improve overall performance
## BI & Deployment Considerations

In a production environment, the most optimium model would be selected for deployment. Furthermore, model predictions would typically be written to a
relational database and surfaced through BI tools such as Power BI.

Potential reporting use cases include:

Monitoring risk score distributions

Segment-level approval rate analysis

Model stability and drift monitoring

This positions the model as a decision-support tool integrated into existing BI
workflows.
## Limitations & Future Work

The dataset is synthetically generated and may not capture all real-world
complexities

Evaluation was performed offline and does not include live performance
monitoring

Future work could explore additional explainability techniques, additional features or real-time
scoring pipelines

