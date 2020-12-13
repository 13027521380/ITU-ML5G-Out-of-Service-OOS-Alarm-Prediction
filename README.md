# ITU-ML5G-Out-of-Service-OOS-Alarm-Prediction
We are from Nankai University, China. The project brought by our team is Out of Service(OOS) Alarm Prediction. 

## Background
In China, there are more than 6 million base stations, which brings huge capital investment including construction cost, operating cost and maintenance cost. China Mobile's total revenue in 2019 was 700 billion, of which one third was used for base station operation and maintenance. In 2021, China will have a 400 billion operation and maintenance market, and the global market will be nearly 1 trillion. So BS investment is increasing year by year.

The traditional maintenance method has the following four steps. Its shortcomings include lacking of real-time performance, high maintenance cost, low efficiency and passive.

The intelligent network maintenance achieves fault prediction through data analysis and continuous self-learning, which can effectively improve processing efficiency and accuracy. 


## Innovation
Innovation 1: Generate labels accurately. which helps accurately predict results. First, fill in missing dates. Like this picture, we should fill in data of March seventeenth. Then, shift up the alarm columns. Owing to label judging by the warnings of the next day, we can use shift function to shift up. Next, add the two columns and determine whether it is non-zero. If non-zero, then label equals 1. Finally, eliminate forecast data and we get the label of training set.

Innovation 2: Threshold adjustment. Looking at the label distribution picture, the training set sample is unbalanced. The ratio of label zero to label one is about 5. We combine the traditional methods—oversampling and under-sampling with the innovation method—threshold adjustment. Adjust the threshold for dividing label according to the ratio of 0 to 1. In this way, we can improve prediction accuracy.

Innovation 3: Multi-dimensional features. The basic features are each type of alarm times. Derived features include …. Comprehensive feature engineering ensures the generalization ability of the model.

## Model Optimization
Our team adopts Gradient Boosting Decision Tree(GBDT) model. It uses the negative gradient value of the loss function as the residual prediction, and continuously linearly superimposes the base model, and finally generates GBDT model. LightGBM is one of the implementation frameworks of the GBDT model, which has the advantage of training fast, high accuracy and low memory usage.


There are three model optimization method: cross-validation, grid search and model merging.

![image](https://github.com/13027521380/zcnku/blob/master/%E5%9B%BE%E7%89%871.png)

## Advantages
(1)High prediction accuracy：Final F1-score is 74.6667%, 1.4% higher than the second place.

(2)Training fast：Model training only takes 3-5 minutes, which is much faster than LSTM model.

(3)Generalization ability：Collect two-year operating data of thousands of base stations to train the model.

(4)Strong expandability：Multi-dimensional predictions can be made by adding features such as power consumption.
