# Project: Predicting Boston Housing Prices
In this project, I will evaluate the performance and predictive power of a model that has been trained and tested on data collected from homes in suburbs of Boston, Massachusetts. A model trained on this data that is seen as a good fit could then be used to make certain predictions about a home — in particular, its monetary value. This model would prove to be invaluable for someone like a real estate agent who could make use of such information on a daily basis.

The dataset for this project originates from the <a href="https://archive.ics.uci.edu/ml/datasets/Housing"> UCI Machine Learning Repository</a> . The Boston housing data was collected in 1978 and each of the 506 entries represent aggregated data about 14 features for homes from various suburbs in Boston, Massachusetts. For the purposes of this project, the following preprocessing steps have been made to the dataset:

- 16 data points have an 'MEDV' value of 50.0. These data points likely contain missing or censored values and have been removed.
- 1 data point has an 'RM' value of 8.78. This data point can be considered an outlier and has been removed.
- The features 'RM', 'LSTAT', 'PTRATIO', and 'MEDV' are essential. The remaining non-relevant features have been excluded.
- The feature 'MEDV' has been multiplicatively scaled to account for 35 years of market inflation.

## Data Exploration:
The dataset originally had 16 data points. I have dropped some of the data points which had less significance in the model.
The features, 'RM', 'LSTAT', and 'PTRATIO', give us quantitative information about each data point. The target variable, 'MEDV', will be the variable we seek to predict. These are stored in features and prices, respectively.
### (a) Feature Observation:


> [i] MEDV VS RM
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/Feature%20Observation/1.png"> 

> [ii] MEDV VS LSTAT
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/Feature%20Observation/2.png">

>[iii] MEDV VS PTRATIO
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/Feature%20Observation/3.png">

## Analyzing Model Performance:
### (a) Learning Curves:
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/learning_curves.png">
The convergence, specially from 300 to 350 points of the curves presented in max_depth=3 shows that is not needed more samples to decrease the error. Adding more points is not necessary due the convergence of training and testing curves. The max_depth=1 indicates underfitting because the R2 score is too low and can not explain verify well the model. The max_depth=6 indicates an approach that will require more data to check if there is a convergence of the curves. It is a little bit overfitted. Finally, the max_depth=10 is totally overfitted, sice the R2 score is near a constant on 100%. There is no indications of convergence of the curves. The model parameters must be reviewed.


### (b) Complexity Curve:
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/complexity_curve.png">
Produced a graph for a decision tree model that has been trained and validated on the training data using different maximum depths. The graph produces two complexity curves — one for training and one for validation. Similar to the learning curves, the shaded regions of both the complexity curves denote the uncertainty in those curves, and the model is scored on both the training and validation sets using the performance_metric function.

### (c) Predicting Selling Prices:
Follow the charts to better understanding of relation of each feature.

> [i] MEDV VS RM
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/Dependency/medv_vs_Rm.png"> 

> [ii] MEDV VS LSTAT
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/Dependency/medv_vs_lstat.png">

>[iii] MEDV VS PTRATIO
<img src="https://github.com/geekquad/Boston-Housing/blob/master/img/Dependency/medv_vs_ptratio.png">



## Applicabilty:
The data must be normalized, so the inflation effects will be adjusted to present monetary values. The features selected gives us a good idea how to describe a feasible price of home. If is available, information like square feet of plot area and pool presence could refine the model. Will require a domain expert validation to check the weigh of each new feature. Yes, we can affirm based on test of 10 triais, the variance was less than 10%, which is a good reference for dealing with unknown data. No, rural city has its own features and characteristics. Must be reviewed if is needed to add or remove features. Yes, the characteristics of the entire neighborhood tend do indicate better conditions to living and development, with more education and less poverty.
