# Richter-Earthquake-Prediction
<hr>


## Background
![dataset.png](https://camo.githubusercontent.com/5090855259d499a5f1e92548bd24dfd6671d2506/68747470733a2f2f63646e2e62726974616e6e6963612e636f6d2f39302f3138323339302d3035302d32323231423936332f65617274687175616b652d4d61702d4e6570616c2d726567696f6e2d74656d626c6f722d74686f7573616e64732d70656f706c652d417072696c2d32352d323031352e6a7067)
On April 25, 2015, there was an earthquake measuring 7.8 on the Richter Scale in Nepal. After the incident, a lot of research and field investigations were carried out to see the damage that occurred to the buildings affected by the earthquake. Due to the large number of buildings and variations of buildings, the post-earthquake investigation process becomes difficult to carry out. However, knowing the description of a building can help us determine the level of damage to the building.

## Audience
This problem can occur all over the world. The use of machine learning can make it easier for disaster management agencies such as  BNPN (Badan Nasional Penanggulangan Bencana) in Indonesia to predict the level of damage to building and estimate losses caused by natural dissasters.

## Dataset
Source dataset retrieved via https://www.drivendata.org/competitions/57/nepal-earthquake/. The data was collected through surveys by Kathmandu Living Labs and the Central Bureau of Statistics, which works under the National Planning Commission Secretariat of Nepal. This survey is one of the largest post-disaster datasets ever collected, containing valuable information on earthquake impacts, household conditions, and socio-economic-demographic statistics. We're trying to predict the ordinal variable damage_grade, which represents a level of damage to the building that was hit by the earthquake. There are 39 columns in this dataset, where the building_id column is a unique and random identifier. The remaining 38 features are described in the section below. Categorical variables have been obfuscated random lowercase ascii characters. The appearance of the same character in distinct columns does not imply the same original value.


## Plan
Efforts to determine the level of damage to a building due to an earthquake will be attempted to be completed by making a model that can predict the level of building damage due to an earthquake. In addition to making prediction models, it will get an overview of the damage that exists in buildings in Nepal and provide recommendations in the form of materials or specific characteristics that can be used in building a building to reduce the impact of damage caused by earthquakes. The model creation process begins with preprocessing data, conducting exploratory data analysis (EDA) processes, building machine learning models based on 7 machine learning algorithms, performing hyperparameter tuning using RandomizedCV, selecting the best model, and making predictions on buildings whose damage level is not yet known.

## Model
Model : https://drive.google.com/drive/folders/1E4cHKwhy-izvzUMdMyHJ2YKzD--1fmeB?usp=sharing

## Conclusion
- After carrying out the Exploratory Data Analysis process, the average level of damage was **2.238272** which stated that the building experienced a moderate level of damage. The complete list is as many as **148259** buildings with medium damage, **87218** buildings with high damage, and **25124** buildings with low damage. It can be seen that the number of buildings with a moderate level of damage is the highest at **56.89%**, followed by buildings with a high level of damage at **33.47%** and finally buildings with a low level of damage at **9.64%**. The higher geographical level between `geo_level_1_id`, `geo_level_2_id`, and `geo_level_3_id` provides information that the higher the geographical level, the more the same level of damage.
- The building recommendations that are considered to be able to minimize the impact of the earthquake are as follows. Buildings using Reinforce Concrete Engineered or Cement Mortar Brick super superstructures. Buildings with 1 or 3 floors. Buildings with normalized height less than 3 meters or more than 9 meters. Buildings with a normalized area of less than 4 square meters or more than 10 square meters.
- The process of predicting the level of damage caused by the 2015 Nepal earthquake to buildings can be predicted using Machine Learning algorithms. The model with the highest F1 Score value in predicting the level of damage due to earthquakes on buildings is the **Extreme Gradient Boosting** algorithm model using the `XGBClassifier` by entering the parameters `n_estimators`=150 and `max_depth`=10. Using this model, the F1 Score value is **73.56%**. Using this model, it can be seen that the 10 most important features in the model are `geo_level_3_id`, `geo_level_2_id`, `area_percentage`, `age`, `geo_level_1_id`, `height_percentage`, `count_families`, `count_floors_pre_eq`, `has_superstructure_timber`, `position_t`. This is in accordance with the situation because `geo_level` which is the geographical area where the building is located is one of the important factors for predicting the level of building damage due to the earthquake. For areas that are located at the epicenter of the earthquake, buildings located in that area will be more easily damaged than buildings that are not. The `area_percentage` and `height_percentage` variables which state the area and height of the building are also important factors for predicting the level of damage caused by an earthquake. It can be seen that the age of the building is also an important factor in predicting the level of building damage due to the earthquake.

## Reference :
- https://blog.clairvoyantsoft.com/correlation-and-collinearity-how-they-can-make-or-break-a-model-9135fbe6936a 
- https://towardsdatascience.com/categorical-encoding-using-label-encoding-and-one-hot-encoder-911ef77fb5bd 
- https://towardsdatascience.com/getting-started-with-xgboost-in-scikit-learn-f69f5f470a97 
- https://towardsdatascience.com/comprehensive-guide-to-multiclass-classification-with-sklearn-127cc500f362 
- https://towardsdatascience.com/comprehensive-guide-on-multiclass-classification-metrics-af94cfb83fbd 
- https://stackoverflow.com/questions/55740220/macro-vs-micro-vs-weighted-vs-samples-f1-score 
- https://stackoverflow.com/questions/44101458/random-forest-feature-importance-chart-using-python 
- https://towardsdatascience.com/xgboost-fine-tune-and-optimize-your-model-23d996fab663 
- https://numpy.org/doc/stable/reference/generated/numpy.argsort.html 
- https://renier-meyer.medium.com/a-very-gentle-introduction-to-multi-class-classification-a57642caab52 
- https://medium.com/analytics-vidhya/accuracy-vs-f1-score-6258237beca2 
- https://towardsdatascience.com/multi-class-metrics-made-simple-part-i-precision-and-recall-9250280bddc2 
- https://towardsdatascience.com/multi-class-metrics-made-simple-part-ii-the-f1-score-ebe8b2c2ca1 
- https://rey1024.medium.com/mengenal-accuracy-precission-recall-dan-specificity-serta-yang-diprioritaskan-b79ff4d77de8 
- https://peltarion.com/knowledge-center/documentation/evaluation-view/classification-loss-metrics/macro-f1-score 
- https://peltarion.com/knowledge-center/documentation/evaluation-view/classification-loss-metrics/micro-f1-score
