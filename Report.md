# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Name: AKHTAR SABIR NASIRUDDIN

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
During the initial training, when I tried to submit the predictions, I realized that Kaggle would reject the submission if there were any negative values in the predictions. Therefore, I needed to make sure that all the predicted values were set to zero if they were negative.

### What was the top-ranked model that performed?
The top-ranked model in my project was the "add_features" model, which achieved a RMSE score of 30.307393 and a Kaggle score of 0.63530. This model was developed by training on additional features that I created through exploratory data analysis and feature engineering.

## Exploratory Data Analysis and Feature Creation
### What did the exploratory analysis find, and how did you add additional features?
The exploratory analysis revealed the distribution of the features in the dataset. To improve the model's performance, I decided to add an additional feature by separating out the datetime column into the hour part. This was done by extracting the hour from the datetime column and creating a new "hour" feature in both the training and test datasets.

### How much better did your model perform after adding additional features, and why do you think that is?
After adding the additional "hour" feature, the model's performance improved significantly. The Kaggle score decreased from 0.63530 to 0.52362, indicating better predictive accuracy. The addition of the "hour" feature allowed the model to capture the time-of-day patterns and their impact on bike sharing demand, leading to improved predictions.

## Hyperparameter Tuning
### How much better did your model perform after trying different hyperparameters?
After performing hyperparameter optimization, the model's performance further improved. The top-ranked model achieved a Kaggle score of 0.52362, which was the best score among all the models trained during the project.

### If you were given more time with this dataset, where do you think you would spend more time?
If given more time with this dataset, I would spend more time on further exploring and engineering features. Additionally, I would experiment with different hyperparameter tuning strategies to see if further improvements in the model's performance can be achieved.

### Create a table with the models you ran, the hyperparameters modified, and the Kaggle score.

| Model            | hpo1                            | hpo2           | hpo3                                | Score   |
|------------------|---------------------------------|----------------|-------------------------------------|---------|
| initial          | prescribed_values               | prescribed_values | presets: 'best quality'          | 1.80439 |
| add_features     | prescribed_values               | prescribed_values | presets: 'best quality'          | 0.63530 |
| hpo (top-hpo-model: hpo1) | Tree-Based Models: (GBM, XT, & XGB) | LightGBMXT     | presets: 'optimize_for_deployment' | 0.52362 |

### Create a line plot showing the top model score for the three (or more) training runs during the project.
 
### Create a line plot showing the top Kaggle score for the three (or more) prediction submissions during the project.
 

## Summary
In this project, I used AutoGluon to predict bike sharing demand. I started with the initial training and realized the need to set negative predicted values to zero for successful submission. The top-ranked model was achieved through hyperparameter optimization, resulting in a Kaggle score of 0.52362. Exploratory analysis helped in identifying the importance of the "hour" feature, which significantly improved the model's performance. If given more time, further feature engineering and hyperparameter tuning could be explored to enhance the model's accuracy.
