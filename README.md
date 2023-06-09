# credit-risk-clarification
Week 20 Challenge: Supervised Machine Learning

The purpose of this analysis is to determine whether the learning model can be recommended for use by a lending services company to build a model that can identify the creditworthiness of borrowers. A set of lending data includes various features of borrowers and whether or not they have defaulted on their loan. The data was split into training and testing datasets. Then the randomoversampler was used on the training dataset to account for the much larger amount of healthy (non-defaulted) loans.

Results of original training data:
* accuracy: 99.18%
* precision for healthy loans: 100%
* precision for risky loans: 85%
* recall for healthy loans: 99%
* recall for risky loans: 91%

The logistic regression model does an okay job at predicting the healthy loans and high-risk loans, however, the precision for the high-risk loan is 85%. This means that if you get stuck in the high risk loan category, there is a 15% chance the loan is being mislabeled as risky. The precision for the high risk loans is 91% despite the precision and recall for the healthy loans being 100%. This indicates that there are indeed false positives (loans that are not actually healthy), but the number is very low compared to the amound of healthy loans. The number of "high risk" loans is much lower than the number of "healthy" loans which is why the precission and recall for both categories are so different.  

Results of RandomOverSampled training data:
* accuracy: 99.38%
* precision for healthy loans: 100%
* precision for risky loans: 84%
* recall for healthy loans: 99%
* recall for risky loans: 99%

After completing the random over sampling, The precision for the risky loans did slightly worse lowering from 85% to 84%. The recall for the high risk loans was significantly better rising from 91% to 99%. This indicates that there are fewer risky loans being mislabeled as healthy (false negatives for risky loans). However, the precision for the risky loans is still in the mid 80s. This indicates that there are still loans that are being mislabeled as risky, but are in facts healthy. 

I would recommend this model. A bank may prefer loans be mislabeled as risky rather than risky loans being mislabeled as healthy, so this model is ideal as the recalls for the the risky loans and healthy loans are both 99% and the precision for the healthy loans is 100%. The precision for the default is only 84%, but this just means the bank may lose out on givng some healthy loans out in favor of having no surprises from miscategorized healthy loans. 