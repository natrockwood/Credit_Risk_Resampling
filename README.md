# Credit Risk Resampling

Credit risk is an inherently unbalanced classification problem, as the number of good loans easily outnumber the number of risky loans. Because of that, it is helpful to use different techniques to train and evaluate models with unbalanced classes. In this challenge, I used imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

#### Random Oversampling
The first technique we used for resampling is the Random Oversampling method. From this method, we made sure that the sizes of both high and low credist risk samples are equal.

We can see from the below classification table that the precision and recall scores from this model are fairly high. 99% of predictions were accurate, and 61% of positive samples were correctly identified. We can also see from our F1 score that this test returns a 75% accuracy rate. We will see if any other models used return higher or lower accuracy ratings to determine which model should be used for this resampling analysis.

The balanced accuracy score for this model is 65%. It is a little bit higher than that of the recall score, however still significant.

![ros](https://github.com/natrockwood/Credit_Risk_Resampling/blob/master/Classification%20Tables/01%20Random%20Oversampling.PNG)

#### SMOTE Oversampling
This next model used is SMOTE oversampling, or the synthetic minority oversampling technique. It is also used to deal with unbalanced datasets.

From the classification table below, the precision and recall scores are also relatively high. With 99% precision score, 69% recall score, and 81% F1 score, these metrics are slightly improved over the metrics of random oversampling. Though the percentage of precisions were about the same for both oversampling techniques, SMOTE oversampling shows a higher accuracy rate. 

The balanced accuracy score for this model is 66%. This percentage is slightly higher that the balanced accuracy of the naive random oversampling model. Given that the F1 score of this model is also higher that that of the other oversampling model, we can say that this is a more reliable model at the moment. We will next explore undersampling and combination sampling to test whether these result is better performance compared to the oversampling models.

![smote](https://github.com/natrockwood/Credit_Risk_Resampling/blob/master/Classification%20Tables/02%20SMOTE%20Oversampling.PNG)

#### Undersampling
For the next model, I used undersampling algorithms to determine if this results in the best performance compared to the oversampling algorithms. For this challenge, I usd the ClusterCentroids resampler.

The classification table shows high precision (99%), though a low recall score of 41%. This means that a lesser number of positive samples were correctly identified. The F1 score is also a low and is not good enough to state that the model will be good at classifying loan status.

The balanced accuracy score of this model is also fairly low at 55%, meaning this is not a reliable model for our classifiers.

![undersampling](https://github.com/natrockwood/Credit_Risk_Resampling/blob/master/Classification%20Tables/03%20Undersampling.PNG)

#### Combination Sampling
Lastly, I used combination sampling to determine if the algorithm results in the best performance compared to the other sampling algorithms above.

We can see that the precision rate is still 99%, which is good. The recall score is higher at 58%, compared to the undersampling algorithm, however still low compared to the oversampling models. The F1 score is 73% is still higher than undersampling, but not oversampling.

Looking at the balanced accuracy score, this reads at 65%, which makes sense given the recal rate is also higher.

![combination](https://github.com/natrockwood/Credit_Risk_Resampling/blob/master/Classification%20Tables/04%20Combination%20Sampling.PNG)

#### Summary of Models
Model               | Balanced Accuracy Score | Precision Score | Recall Score | F1 Score |
------------------- | ------------------------|-----------------|--------------|----------|
Random Oversampling | 65%                     | 99%             | 61%          | 75%      |
SMOTE Oversampling  | 66%                     | 99%             | 69%          | 81%      |
Undersampling       | 55%                     | 99%             | 41%          | 58%      |
Combination Sampling| 65%                     | 99%             | 58%          | 73%      |

From the summary above and their individual classification reports, I can confidently say that the SMOTE Oversampling algorithm is the bst model to use for resampling this data.
- The balanced accuracy score is higher than the others at 66%, which means that this model performs better.
- From this model, the precision and recall scores are high. 99% of predictions were accurate, and 69% of positive samples were correctly identified. These scores are higher than any of the other models. Given the F1 score is also the highest of the 4 models, we can say that the SMOTE Oversampling model is the most accurate and it is the model I'd reccommend using.
