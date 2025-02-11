# **Challenge-14 Machine Learning Trading Bot**
In this Challenge, you’ll assume the role of a financial advisor at one of the top five financial advisory firms in the world. Your firm constantly competes with the other major firms to manage and automatically trade assets in a highly dynamic environment. In recent years, your firm has heavily profited by using computer algorithms that can buy and sell faster than human traders.

The speed of these transactions gave your firm a competitive advantage early on. But, people still need to specifically program these systems, which limits their ability to adapt to new data. You’re thus planning to improve the existing algorithmic trading systems and maintain the firm’s competitive advantage in the market. To do so, you’ll enhance the existing trading signals with machine learning algorithms that can adapt to new data.

## **Instructions:**
Use the starter code file to complete the steps that the instructions outline. The steps for this Challenge are divided into the following sections:

  - Establish a Baseline Performance

  - Tune the Baseline Trading Algorithm

  - Evaluate a New Machine Learning Classifier

  - Create an Evaluation Report

## **Establish a Baseline Performance**
In this section, you’ll run the provided starter code to establish a baseline performance for the trading algorithm. To do so, complete the following steps.

Open the Jupyter notebook. Restart the kernel, run the provided cells that correspond with the first three steps, and then proceed to step four.

  1. Import the OHLCV dataset into a Pandas DataFrame.

  2. Generate trading signals using short- and long-window SMA values.

  3. Split the data into training and testing datasets.

  4. Use the ```SVC``` classifier model from SKLearn's support vector machine (SVM) learning method to fit the training data and make predictions based on the testing data. Review the predictions.

  5. Review the classification report associated with the ```SVC``` model predictions.

  6. Create a predictions DataFrame that contains columns for “Predicted” values, “Actual Returns”, and “Strategy Returns”.

  7. Create a cumulative return plot that shows the actual returns vs. the strategy returns. Save a PNG image of this plot. This will serve as a baseline against which to compare the effects of tuning the trading algorithm.

  8. Write your conclusions about the performance of the baseline trading algorithm in the ```README.md``` file that’s associated with your GitHub repository. Support your findings by using the PNG image that you saved in the previous step.

## **Tune the Baseline Trading Algorithm**
In this section, you’ll tune, or adjust, the model’s input features to find the parameters that result in the best trading outcomes. (You’ll choose the best by comparing the cumulative products of the strategy returns.) To do so, complete the following steps:

  1. Tune the training algorithm by adjusting the size of the training dataset. To do so, slice your data into different periods. Rerun the notebook with the updated parameters, and record the results in your ```README.md``` file. Answer the following question: What impact resulted from increasing or decreasing the training window?
> **Hint** To adjust the size of the training dataset, you can use a different ```DateOffset``` value—for example, six months. Be aware that changing the size of the training dataset also affects the size of the testing dataset.

  2. Tune the trading algorithm by adjusting the SMA input features. Adjust one or both of the windows for the algorithm. Rerun the notebook with the updated parameters, and record the results in your ```README.md``` file. Answer the following question: What impact resulted from increasing or decreasing either or both of the SMA windows?

  3. Choose the set of parameters that best improved the trading algorithm returns. Save a PNG image of the cumulative product of the actual returns vs. the strategy returns, and document your conclusion in your ```README.md``` file.

## **Evaluate a New Machine Learning Classifier**
In this section, you’ll use the original parameters that the starter code provided. But, you’ll apply them to the performance of a second machine learning model. To do so, complete the following steps:

Import a new classifier, such as ```AdaBoost```, ```DecisionTreeClassifier```, or ```LogisticRegression```. (For the full list of classifiers, refer to the [Supervised learning page](https://scikit-learn.org/stable/supervised_learning.html) in the scikit-learn documentation.)

Using the original training data as the baseline model, fit another model with the new classifier.

Backtest the new model to evaluate its performance. Save a PNG image of the cumulative product of the actual returns vs. the strategy returns for this updated trading algorithm, and write your conclusions in your ```README.md``` file. Answer the following questions: Did this new model perform better or worse than the provided baseline model? Did this new model perform better or worse than your tuned trading algorithm?

## **Create an Evaluation Report**
In the previous sections, you updated your ```README.md``` file with your conclusions. To accomplish this section, you need to add a summary evaluation report at the end of the ```README.md``` file. For this report, express your final conclusions and analysis. Support your findings by using the PNG images that you created.


***


# **_Evaluation Report_**
The following sections outline the comparison and analysis of different Machine Learning methods:

## **_Establish a Baseline Performance_**
The baseline training data is 3 months from the beginning of the dataset. 
The baseline performance utilizes a SVC classifier model and generates signals using different SMA values (short window = 4 days vs long window = 100 days). 
The accuracy rate is 0.55.

![image](https://user-images.githubusercontent.com/103230949/180673091-f511c725-4ce3-46db-8b5c-d920a09f3abd.png)

![image](https://user-images.githubusercontent.com/103230949/180673209-49baf394-5f7c-4f80-9b6c-37f8c2fad4ea.png)

## **_Tune the Baseline Trading Algorithm_**
Modified training data window, increased from 3 months to 6 months.
The new performance with modified training data has an accuracy rate of 0.56.

![6 month training set](https://user-images.githubusercontent.com/103230949/180693016-f480b997-b51f-40a2-8ea4-db3628745ba2.png)

![hvplot_6 month training set](https://user-images.githubusercontent.com/103230949/180693032-bfa55e89-cbe1-4501-9b3a-b59e217c922a.png)

It seems like when we increased the training window, it actually imporved our model's accuracy and cumulative returns. Not so much when we decreased the training window when compared to the original data.

## **_Evaluate a New Machine Learning Classifier_**
In this section, we utlized a new machine learning classifier called LogisticRegression with all input parameters the same as the original dataset.
The new machine learning classifer has lower accuray rate of 0.52.
We should continue to utlize the original machine learning method but try to improve the model by increasing the training period. 

![lr_3 month training set](https://user-images.githubusercontent.com/103230949/180694176-8241203b-6e38-4009-8096-f8560bef078a.png)

![lr_hvplot_3 month training set](https://user-images.githubusercontent.com/103230949/180694181-d14e4116-6ae4-4e23-a3bd-fc11aa1b9691.png)
