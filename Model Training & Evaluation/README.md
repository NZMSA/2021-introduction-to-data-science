## Model Training & Evaluation

Following on from the Data Preparation section, we've now cleansed the data and can begin with the model training and evaluation. In this workshop, we have chosen to follow a straightforward approach of taking the mean accuracy to score and compare models.

In this workshop, we've selected a few common models you'll most likely encounter when studying data science. We haven't covered all the models available in scitkit-learn, so feel free to explore even more on: https://scikit-learn.org/stable/index.html

What makes the scitkit-learn library so powerful as a data science solution is the simplicity of training and evaluating the models. We can train and evaluate a model in less than 5 lines.

In this workshop, we are given the test and train sets as-is which means we don't have to perform a test-train-split to produce them. Usually what would happen is that we would take the original data set and split it into a x-train, x-test, y-train, and y-test. We can then fit the model; Generally all scit-kit models are fit in through the same procedure with: ``model.fit(x_train, y_train)``. We can then predict on our test set with: ``y_pred = model.predict(x_test)``, this takes our x features and produces prediction for each row in ``x_test``. Once we've performed the prediction, we can get the model accuracy by comparing our prediction to the actual output as follows: ``metrics.accuracy_score(y_test, y_pred)``. As mentioned most sci-kit learn models will follow this general form allowing you to model data across many different models available within the library with ease.

We also discussed cross-validation with the purpose of ensuring that we have a generalised model which is unaffected by overfitting or selection bias. This can be simply done in scikit-learn with: ``cross_val_score(model, x_train, y_train, cv=10)``. The ``cv`` parameter defines the number of folds we want to perform with cross-validation.

It's worth noting that not all data sets can be cleaned to the extent you will encounter in this workshop. So you will have situations where you will need to handle NaN values in your data. It may require you investigating how the NaN values occur and investigate why such pattern exists. Some of the methods to handle these NaN values include:

* Fill NaN with the mean/median value
* Create a model to predict the NaN values.
* Drop rows with NaNs

