Insights and Conclusions¶
Confusion Matrix, Type 1 and Type 2 Errors
The confusion matrix records the number of true positives, false positives (type 1 error), true negatives and false negatives (type 2 errors) and hence gives a clear indication about how well the model performs.
While in most cases type 1 errors are considered more serious, however, in our case false negatives, that is, incorrectly predicting that a customer will not leave the bank is a more serious error. This is because such a false prediction would fail to warn the bank and would keep them from pursuing preventive measues.
Whereas, the type 1 error also has its down sides, here a false positive implies incorrectly predicting that a customer will leave the bank. In such cases, the bank will need to look into the customer and pursue possibly unecessary preventive measures, which might lead to loss of time and resources.
Precision: = tp / (tp + fp) [higher the value, lower the number of false positives]
Recall = tp / (tp + fn) [higher the value, lower the number of false negatives]
Since, in our case we seek to minimise the number of false negatives, hence we try to ensure a high recall value. Amongst our models, the random forest appears to have the highest recall value, although the precision is even higher.
Accuracy = (tp+tn)/(tp+tn+fp+fn)
Since we have balanced out the dataset, accuracy is a good evaluation metric. Again, the closer the accuracy value is to 1, the better the model performs.
Model insights:
Tree Based Models:
Decision trees and random forests are used for both regression as well as classification tasks. Since, our problem consists of predicting one out of 2 (finite) possible outcomes viz. the customer leaves or the customer does not leave, hence ours is a binary classification model.
One of the most popular advantages of using tree based algorithms is their immunity towards outliers and variation in the data. Hence these algorithms do not necessarily need outlier treatment and feature scaling. Since our data does have a significant number of outliers, tree based algorithms can help avoid going through the time consuming outlier handling process.
Our data consists of both continuous as well as categorical data however, trees can handle qualitative variables without the need to create dummy variables.
Since random forests and gradient boost are both ensemble methods, that use multiple decision trees, they prevent overfitting as well as have a greater acccuracy as is seen in our case.
K Nearest Neighbour Classifier
The algorithm has its foundation on calculating distances between input point and training points and choosing K closest points to classifiy the input point.
There are different kinds of distance formulas this algorithm can use such as the Euclidean distance, Manhatten distance etc. However, it is clear that this algorithm can be computationally expensive when dealing with large datasets, as in our case. The larger the dataset, the more is the time and cost of its implementation, and hence its degraded peformance.
Again, since this algorithm involves computing distances between points, dimensionality reduction and feature scaling are necessary. In addition, the KNN classifier is highly sensitive to outliers and missing values, thus making it completely necessary to carry out all these preprocessing steps.
The most important step this algorithm involves is to identify the best value of k. This involves various trial and error runs or using a hyper parameter tuning technique such as grid search cv, thus further adding to the heavy computation it involves.
All the above factors may have had an important role to play in its less impressive performance in our use case.
We learn that KNN might not be the best algorithm for data that is big in size or dimension or that has significant nummber of missing values and/or outliers (as in our case).
Conclusion
Having considered various evaluation metrics and the ROC curve, we can conclude that the gradient boosting classifier is the best performing algorithm for our data amongst the other explored models to study and predict customer churn behaviour. This model can help the bank predict which customers might consider leaving. With such information, the bank can proactively prevent the customer from leaving by addressing the issues the customers might be facing that incentivized them to consider leaving.
