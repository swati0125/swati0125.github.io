## Automated Ad Classification
[GitHub](https://github.com/abhinav314/adClassification)

### Business Context

Craigslist.com is one of the most visited web pages on the internet. An estimated 80 million advertisements are posted monthly. Out of these approximately **7% of ads are misclassified** leading to a substantial loss in revenue. Our aim in the project was to develop a framework that identifies misclassified advertisements and puts them into the correct categories. We focused our solution on *two categories - cars & general*. Geographically our scope was confined to *Chicago, Indianapolis and Lafayette (Indiana)*.

### Data Preparation

I scraped around 6k ads from regional Craigslist websites. The ad body and various tags such as price, condition, miles driven made up our data set.
The data was then tokenized into 4-grams, lemmatized, cleaned of stop words and punctuations and vectorized before being fed into the models for training.
My team manually tagged close to 6000 ads for model training.

![alt text](/images/nlp1.png "Data Processing")

### Modeling Techniques

I trained various classification models (linear regression, bagging, boosting, multi-layer perceptron and Long Short Term Memory). I attained an accuracy of 96% using a Long Short Term Memory model and 97.5% using Multi-level Perceptron model on test sets

![alt text](/images/nlp2.png "Model Performance")

### Business Outcomes

Our solution is dynamic, and can be applied across other categories to identify and correct misclassified ads.

![alt text](/images/nlp3.png "Outcomes")