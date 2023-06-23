# Gaming Habits & Generalized Anxiety Disorder 
![Gaming Setup](https://github.com/asoylatte03/osf_gaminganxiety/blob/main/images/blurrystock-HIbAmybJHVs-unsplash.jpg)

## Library Prerequisites
This project utilizes several key data science packages such as: 
- Pandas
- Scikit-learn
- Numpy
- Matplotlib
- Seaborn

In addition, this project relies on additional libraries for data visualizations and modeling such as `plot-likert` and `xgboost`
```
pip install plot-likert  
```
```
conda install -c conda-forge py-xgboost
```
## Business Problem & Stakeholder Understanding 
Healthy Gamer (HG) is a non-profit organization that aims to improve the mental wellness of the “internet generation” through evidence-based interventions, meditation,  and psychiatric principles. Healthy Gamer is interested in developing a coaching program for parents with anxious teens. They are interested in understanding the key features involved in predicting the severity of anxiety so as to recommend resources and guidance to parents. 

## Project Overview
This project seeks to develop a predictive model to classify the severity of anxious behavior patterns among teen gamers and explain the influence of various predictors. 

## Data
This project utilizes data collected from an online database from the Center for Open Science. Data is from an online survey of more than 13,000 gamers. The authors of the database surveyed participants' demographics (e.g., Gender, Age), gaming habits (e.g., game most frequently played, hours played, platform used), and used a variety of psychometric scales (e.g., Generalized Anxiety Disorder Screener (GAD-7), Social Phobia Inventory (SPIN), etc.)

More information on the dataset can be found online at the [Center for Open Science database](https://osf.io/vnbxk/) as well as a copy of the survey used and detailed variable descriptions. 

## Method 
In order to best determine the best classification model and algorithm, an iterative process was used. A baseline model was first constructed using `DummyClassifier()`. Next, for each classification algorithm tested, a baseline model was first constructed, then a hyperparameter tuned model was constructed, and finally, to address the class imbalance for anxiety severity, SMOTE was used alongside the baseline model. Each model was compared to the `DummyClassifier()` to determine the best model to represent each classification algorithm chosen. Finally, the best models for each classification algorithm were compared with the baseline `DummyClassifier()` model to determine the single-best model for predicting the target classes. 

## Baseline Model 
A baseline model using `DummyClassifier()` was first constructed to compare future iterative models against. The baseline model had the following classification metrics:
- accuracy: 40% 
- precision: 40% 
- recall: 40% 
- f1-score: 40% 


## Model Evaluation 
![Classification Metrics](https://github.com/asoylatte03/osf_gaminganxiety/blob/main/images/model_classification_metrics.png)
Using the best model for each classification algorithm tested, accuracy, precision, recall, and f1-score were evaluated across each model. The above visualization shows a side-by-side comparison of the best models for each classification algorithm tested. 

## Best Model 
The best model for determing the target classes was a hyperparamater tuned XGBoost model. The XGBoost model had the following classification metrics: 
- accuracy: 62%
- precision: 63% 
- recall: 61% 
- f1-score: 61%


## Feature Importances 
![Feature Importance](https://github.com/asoylatte03/osf_gaminganxiety/blob/main/images/feature_importances.png)
The best XGBoost model determined that the following features were strong indicators of predicting the target classes (i.e., anxiety severity)
- Participants responses on the `GADE`, an optional question assesing the degree to which anxious behavior patterns affects different aspects of a participant's life 
- Participant's motivation for playing games being "winning" 
- Participants being born in Romania 
- Participants identifying as male 
- Hours played in a given week
  
## Key Recommendations & Actions 
Based on the strength of features used in predicting anxiety severity the following recommendations are presented: 

### GADE 
Healthy Gamer should emphasize, to parents, how understanding anxious attitudes affect different aspects of their child’s life (e.g., professional settings, interpersonal or familial relationships). HG can recommend parents working with children to develop sustainable routines adapted around their gaming habits. 

### Motivation for Playing 
Emphasive how understanding a child’s motivation for gaming(e.g., winning) relates to their child's anxious behavior patterns and attitudes. HG can recommend that parents communicate with their children about their motivations behind gaming and develop a compassionate relationship adapted around their gaming habits. 

### Hours Played 
Emphasive monitoring the amount of hours played per week and provide educational resources for parents to learn how to set effective boundaries and limits on hours spent gaming. HG can recommend that parents set healthy boundaries and limits on hours spent gaming. HG can advocate for parents to model effective and responsible tech usage for their children. 

## Disclaimer
This project uses Healthy Gamer as a hypothetical stakeholder and was not endorsed by Healthy Gamer. The insights and recommendations shared in this project do not seek to express or represents the views of Healthy Gamer as a whole. More information on Healthy Gamer's mission to address gaming addiction can be found [here](https://healthygamer.gg/)
