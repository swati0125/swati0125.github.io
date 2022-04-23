## Bankruptcy Prediction
[GitHub](https://github.com/abhinav314/bnkruptcyEnsemble)

### Business Context

The objective of the project was to develop a predictive model that combines various econometric measures to foresee a financial condition (bankrupt or not) of a firm based on a financial balance sheet data set available on Kaggle.

### Data Processing

The dataset provided was highly imbalanced and skewed. We tried several pre-processing techniques some of which did not perform well in terms of reducing bias and variance.

Finally we went with dropping duplicates, over-sampling and stratified K-sampling techniques, in order to reduce skewness and balance positive and negative classes.

![alt text](/images/dm1.png "Data Pre-processing techniques")

### Model Selection

This was a classification problem. My team had to predict whether a firm would go bankrupt (class 1) or not (class 0).

To solve the problem, we started with simple linear models such as regularized logistic regression, and support vector classifiers. These models did not perform well and we moved on to bagging and boosting algorithms.

Trying out stand-alone models such as AdaBoost, Random Forest and xGBoost, we realized that while the models performed well on the training set, all of them were prone to overfitting. Hence, I decided to use an ensembling technique called Stacking Cross Validation Classifier.

A StackedCVClassifier has two layers. The outer layer consists of an ensemble of models - in our case we noticed AdaBoost, lightGBM and Random Forest worked the best. Next, there is a meta model. The predictions of the outer layer are voted and the most probable predictions are then fed into the meta model as data points. The meta model tries to reduce the residuals. In our case we chose xGBoost as the meta model.

![alt text](/images/dm2.png "Model Selection")

### Final Model

The metric to be optimized was Area Under the Curve (AUC) for a ROC curve. An ROC curve plots Sensitivity on the y-axis and (1 - Specificity) on the x-axis, thereby optimizing the model for both classes.

Using the StackedCVClassifier we achieved an AUC score of 95.5% on the training data, and 96.25% on the test data. Hence, my team was able to build a robust and scalable model.

![alt text](/images/dm3.png "Stacking CV Classifier Performance")