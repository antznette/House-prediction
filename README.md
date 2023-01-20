# House-prediction


Linear regression is a type of supervised learning that uses inputs x to predict an outcome Y. It approximates a causal link between two or more variables linearly. Input X can take different values depending on whether it's a simple or multiple linear regression.
We use simple and multiple regression to predict house price, the task's goal variable. While multiple regression focuses on the best-fitting model, simple regression is always about the line that fits the data the best. The lowest sum of square error is our goal.
Model 4 is the most efficient since it predicts better and has the greatest r2 score (0.728).
The House price.py file contains all of the work's source code.
No missing values were found when I looked at my data, so I used a heat map to plot a correlation of the characteristics to help me decide which ones to use as the inputs for my regression.

Modelling
Each time a regression is created, it should be meaningful. Critical thinking is most times needed for regression. Before concluding a feature is significant, always try to understand why. One of the ways to achieve this is by checking the correlation of the input variables to the target. But it is essential also to note correlation does not always mean causation.
For each model, we slice the input and target variables x and y using the iloc method and split the data into test and train. Splitting mainly aims to ensure the model trains on a set of samples it has never seen before. The split can either be done 60/40,70./30, 80/20, or even 90/10. Ensuring the test sample is smaller than the training sample is essential. These test/train data are used to fit the learning algorithm so that it can learn how to predict.
We create an instance of the linear regression class and then fit the regression in the correct order(x,y).

Evaluation and Model improvement

The coefficient of determination (R2_score) measures the goodness of fit of a model. It explains the percentage variability of the model. It helps with the effectiveness of a model
In general, a house's size has a significant impact on price, which explains its strong correlation to price. However, as previously mentioned, correlation does not always imply causation. Using square feet living to predict house price in model1 gives an r2_score 0.49. In the ideal circumstance, the residual plot should follow a normal distribution. In this instance, we see that there are a lot of positive residuals and a small number of negative residuals (far from the mean). Positive values indicate that y-hat (predictions) is substantially lower than y-train (the targets), and vice versa, given the definition of the residuals (y-train - y-hat). This indicates that our model does a terrible job of predicting expensive houses. This is food for thought to improve our model. This provides ideas for enhancing our model.
I personally tried working with different feature pairings, however the model 4 with 7 features had the best r2 score. The discrepancy between the target and projected values is referred to as residual and is used to assess a model's efficacy. The distribution is nearly normal, although model 4 consistently undervalues prices while seldom overestimating targets. Based on this, we can continue to look into methods to improve our models.


Visualization
Prediction plot for model 4 test set- This also helps check efficiency of the model.
We can also figure out how much the predictions and targets differ from one another. Remember that this is the residual. This comparison is incredibly valid because OLS simply reduces the whole sum of squared errors (residuals). Seeing how far we are from the outcome in terms of percentage makes sense as a final step. To simply sort the data set, we take the absolute difference in % in this case.


Conclusion
Training the model with more features will improve the model. Generally, the more features included, the higher the r2 score, but we can add 100 input variables to a model making the predictions outstanding, but this greatly makes regression futile. It's best to use a few input variables to predict the model, as a good model is always better than a model with high explanatory power. The adjusted R2 should be used to remove meaningless input variables.
Improving the model
Outliers are observations that are abnormally distant from other observations in the data. They have a significant impact on regression and inflate coefficients as regression tries to draw the line closer to those values. The model can be enhanced by eliminating outliers. We may accomplish this using a number of quantile or log transformation techniques.
Changing the random state of your data set can also help improve the model, as a model might train/test better on one group than the other. It is best to take the average of the different random states.
Applying some other machine learning algorithms like random forest, svm might give a better result. Also, hyper parameter tuning of the regression result can give a higher score.
Worthy of note is that the r2_score for the test set should always be lower than those of the train test. That way, you can be sure your model has not overfitted.
In conclusion, Model 4 is best for this task but adding more features can improve the model even further.
