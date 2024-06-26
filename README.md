## PREDICTING H1N1 FLU VACCINATION STATUS USING MACHINE LEARNING

![Vaccination_logo](Images/PIC.jpg)

## Project Overview

The aim of this study is to predict how likely individuals are to receive their H1N1 flu vaccine.I believe the prediction outputs (model and analysis) of this study will give public health professionals and policy makers, as an end user, a clear understanding of factors associated with low vaccination rates. This in turn, enables end users to systematically act on those features hindering people to get vaccinated.

In this project, I used the survey data from the National Flu Survey (NHFS, 2009) to predict whether or not respondents got the H1N1 vaccine. It is important to understand past vaccination patterns in order to understand those of more recent pandemics, such as COVID-19. The most influential factors determining vaccination status are found to be:-
1. Doctor Recommendation of H1N1 vaccine
2. Health Insurance, 
3. Opinion of H1N1 Vaccine Effectiveness
4. Opinion of H1N1 Risk by our final model.

 I used six machine learning models to make the predictions. We used:-
 1. Decision Tree Classifier.
 2. Logistic Regression.
 3. Random Forest.
 4. K-Nearest Neighborhood Classifier.
 5. Gradient Boosting Classifier. 
 6. XG Boosting Classifier. 

The XG Boosting Classifier yielded the best accuracy and precision score.

So as to classify exactly those who got H1N1 flu shot from those that did not, we need a higher accuracy of the model outputs, as well as a high precision score, which is related to a low false positive rate (those who predicted to be vaccinated but did actually not get H1N1 flu shot). 

## Data Overview

This data comes from a NHFS National Flu Survey from 2009, which inquires about whether or not people received the seasonal flu and/or the H1N1 flu vaccination, as well as their demographic, behavioral, and health factors. There are 26,000 respondents to this survey. In this project I chose H1N1 vaccination rate as our target variable. I used all features in the survey, and filled missing values using the Iterative Imputer.


## Methodology

I wanted to use a variety of different models so as to find the most accurate model. Because there are many different hyperparameters for each model and I did not know the optimal combinations, I used GridSearrchCV to find the best combinations for each model. I specified class weight to be balanced in order to address the class imbalance issue for our models, whenever possible. 

I also analyzed the accuracy score, precision score, fl score, and roc-auc curve for each model. I also compared the different roc-auc curves of each model, to choose the final model. Additionally, I looked closely at the confusion matrix to see whether or not we were minimizing false positives. XG Boosting Classifier gave us the best accuracy and precision scores, so we chose it to be our final model.

## Project Results

![Vaccination_logo](Images/Comparsion-AUC-Models.png)

The XG Boosting Classifier model has the highest overall scores of all the models done so far, and also does the best job of minimizing the false positives. This  model did not overfit to the training set, I got similar AUC, precision and accuracy scores for the holdout set. Because the model does a good job of minimizing the false positive rate on the hold out data, I am fairly confident that it will generalize well to unseen data and will accurately help public health offials determine the people who didn't get the vaccine. 

I also looked into feature importances to understand the relationship between the features and vaccination behavior. I saw that the demographic and behavioral features are not that important compared to health related factors and opinions. 

The doctor recommendation, health insurance, opinion of vaccine efficiency, and opinion of H1N1 risk are the top important factors in determining people's vaccination status.

## Conclusion

I recommend that public health officials at the American Public Health Association (APHA) communicate to doctors the importance of recommending to patients that they get the H1N1 vaccine. I also recommend that they find a way to make the vaccine accesible to people regardless of health insurance status.

Additionally, because opinion on H1N1 vaccine effectiveness and H1N1 risk to health are highly influential in determining vaccination status, I recommend that the APHA make educational outreach a priority. Our analysis might not fully resolve the goal of predicting H1N1 vaccination status because I was not able to fully rule out false negatives, or people who I predicted as not getting vaccinated but actually did get the vaccine. Additionally, there may be other factors at play which were not tapped into by this survey's questions which could also play a role in vaccination prediction. 

## Next Steps

For the next steps, I would like to look at more recent flu survey data, so as to get the most recent results. I would also like to do more feature engineering to improve accuracy. Lastly, since I chose to focus only on predicting H1N1 vaccination status, I would like to focus in the future on predicting seasonal flu vaccine status.


## Repository Navigation

### Data:
- https://www.drivendata.org/competitions/66/flu-shot-learning/page/213/


### Notebooks
- Final notebook: https://github.com/laaria-chris/H1N1-VACCINATION-PREDICTION-MODEL/blob/main/MAIN_NOTEBOOK.ipynb
- Notebook PDF:  https://github.com/laaria-chris/H1N1-VACCINATION-PREDICTION-MODEL/blob/main/MAIN_NOTEBOOK.pdf

### Presentation

- https://github.com/laaria-chris/H1N1-VACCINATION-PREDICTION-MODEL/blob/main/Phase3-Project-slides.pdf

