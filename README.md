# Credit_Risk_Analysis

# Overview 
FastLending, a peer-to-peer lending service, wants to use machine learning to build models that predict credit risk. They want to use these models to provide a quicker and more accurate service for customers. They also believe that machine learning will help find best qualified candidates and lower default rates.

# Results 

## Naive Random Oversampling 


![Naive Random Oversampling Results](https://user-images.githubusercontent.com/100237685/180667228-dc6c201d-3993-4153-927b-e1d5cf79140e.png)
* The accuracy score is 71%, which is a good range to be in as it is not too accurate (overfit), but accurate enough to be a reliable model. 
* However, when we look at the confusion matrix, we can see that the majority of the accuracy seems to work only for predicting 1 (or low risk) but not 0 (or high risk). This indicates that this model would accurate but not precise. 
* If you look at the classification report, my point is further proved by the incredibly low precision score for 0 (high risk) loan status, and the perfect precision score for 1 (low risk). 
* This model would not be useful in finding high risk applicants. 


## SMOTE Oversampling


![SMOTE Oversampling Results](https://user-images.githubusercontent.com/100237685/180667316-8397d90a-14a4-43b9-8c37-b9e2212d2acf.png)


* This model is very similar to the precision of the Naive Random Oversampling.
* The accuracy score, however, is much worse at 49%.
* I would not recommend using this model as it has very low accuracy and precision.


## Undersampling


![Undersampling Results](https://user-images.githubusercontent.com/100237685/180667409-79e0b3a9-3646-4a69-b10a-df19225d594e.png)


* Again, this model is also similar to the precision of the Naive Random Oversampling. It is slightly worse at finding low risk candidates yet slightly better at finding high risk candidates.
* The accuracy score is 72%, which is only 1% higher than Naive Random Oversampling. As such, it's still not a good model for finding high risk applicants. 


## Combination Over and Under Sampling


![Combination Over and Under Sampling](https://user-images.githubusercontent.com/100237685/180667460-1d7983b0-5895-4207-8e8f-b79f23347786.png)


* This model is marginally better than the previous ones as it has a 73% accuracy score and 0.02 for precision of finding high risk applicants vs the 0.01 we've been seeing. 
* Regardless, I still wouldn't recommend using the model as it still wouldn't be good for finding high risk applicants. 


## Easy Ensemble AdaBoost Classifier


![Easy Ensemble AdaBoost Classifier](https://user-images.githubusercontent.com/100237685/180667497-f69ec732-f7e6-4f39-a66f-6dec6582c811.png)


* The AdaBoost Classifier is interesting because at first glance, it looks as though it would be a great model with a 99% accuracy score. 
* Upon closer inspection however, we see that the accuracy is all towards finding low risk applicants; it did not accurately predict a single high-risk applicant.
* In addition, even if it had found high risk applicants, a 99% accuracy score means that this model is overfit to the data. The data that is being used by FastLending isn't stagnant, so the model they chose has to be able to adjust with the changing data they feed it. 
* As a result, I would not recommend this model for finding high risk applicants. 


## Balanced Random Forest Classifier


![Balanced Random Forest Classifier pt 1](https://user-images.githubusercontent.com/100237685/180667563-6ca75f0a-c289-45b2-bd73-b0bdbc55b8ab.png)
![Balanced Random Forest Classifier pt 2](https://user-images.githubusercontent.com/100237685/180667568-9b203a72-33a9-4c48-8b8d-ea229bc9db71.png)
![Balanced Random Forest Classifier pt 3](https://user-images.githubusercontent.com/100237685/180667570-4acdfa50-02f5-4154-a13c-612d3f5e2de0.png)


* An accuracy score of 66% doesn't seem great at first in comparison to the 71-73% we saw in previous models, but if we look closer at the data, we'll see that this model actually predicts high risk applicants the best out of all of them. 
* The precision score for finding high risk applicants is 0.68, the highest we've seen.
* That being said, even though this model is good at finding high risk applicants, it finds very few of them. It could be that the scale weights need to be adjusted.
* This model does provide other useful information though, such as the features of a candidate’s application that are the biggest influence on whether they're high risk or not. 
* It appears that the top three influences are: total recurring interest, last payment amount, and total payment invoiced. 
* This model could be a helpful tool in finding high risk applicants, but I would not use it on its own. 

# Summary
All of these models have their vices and virtues, but truthfully, I would not use any of them on their own to uncover high risk applicants. Most of them are skewed towards accurately finding low risk applicants, which can be good, but there are a number of high-risk applicants that slip through the cracks. 


The Balanced Random Forest Classifier comes the closest to being a good model, but it's still heavily favoring low risk applicants. If the scaling was done differently than perhaps it would be better. However, it does provide interesting insight into what influences a candidate’s potential to be high or low risk. That information could prove to be useful to FastLending. It might be beneficial to combine the Balanced Random Forest Classifier with another model type to provide the results the company is looking for.
