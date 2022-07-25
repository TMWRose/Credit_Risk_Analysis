# Credit_Risk_Analysis

# Overview 
FastLending, a peer to peer lending service, wants to use machine learning to build models that predict credit risk. They want to use these models to provide a quicker and more accurate service for customers. They also beleive that machine learning will help find best qualified candidiates and lower defualt rates.

# Results 

## Naive Random Oversampling 


![Naive Random Oversampling Results](https://user-images.githubusercontent.com/100237685/180667228-dc6c201d-3993-4153-927b-e1d5cf79140e.png)
* The accuracy score is 71%, which is a good range to be in as it is not too accurate (overfit), but accurate enough to be a reliable model. 
* However, when we look at the confusion matrix, we can see that the majority of the accuracey seems to work only for predicting 1 (or low risk) but not 0 (or high risk). This indicates that  this model would accurate but not percise. 
* If you look at the classification report, my point is further proved by the incredibly low precision score for 0 (high risk) loa status', and the perfect precision score for 1 (low risk). 
* This model would not be useful in rooting out high risk applicants. 


## SMOTE Oversampling


![SMOTE Oversampling Results](https://user-images.githubusercontent.com/100237685/180667316-8397d90a-14a4-43b9-8c37-b9e2212d2acf.png)


* This model is very similar to the percision of the Naive Random Oversampling.
* The accuracy score, however, is much worse at 49%.
* I would not reccomend using this model as it has very low accuray score and percision.


## Undersampling


![Undersampling Results](https://user-images.githubusercontent.com/100237685/180667409-79e0b3a9-3646-4a69-b10a-df19225d594e.png)


* Again, this model is also similar to the percision of the Naive Random Oversampling. It is slighty worse at finding good candidiates yet slightly better at finding high risk candidates.
* The accuracy score is 72%, which is only 1% higher than Naive Random Oversampling. As such, it's still not a good model for finding high risk applicants. 


## Combination Over and Under Sampling


![Combination Over and Under Sampling](https://user-images.githubusercontent.com/100237685/180667460-1d7983b0-5895-4207-8e8f-b79f23347786.png)


* This model is marginaly better than the previous ones as it has a 73% accuracy score and 0.02 for percision of finding high risk appplicants vs the 0.01 we've been seeing. 
* Regardless, I still wouldn't reccomend using the model as it still wouldn't be good for finding high risk applicants. 


## Easy Ensemble AdaBoost Classifier


![Easy Ensemble AdaBoost Classifier](https://user-images.githubusercontent.com/100237685/180667497-f69ec732-f7e6-4f39-a66f-6dec6582c811.png)


* The AdaBoost Classifier is interesting because at first glance, it looks as though it would be a great model with a 99% accuracy score. 
* Upon closer inspection however, we see that the accuracey is all towards finding low risk applicants; it did not accurtley predict a single high risk applicant.
* In addition, even if it had found high risk applicants, a 99% accuracy score means that this model is overfit to the data. The data that is being used by FastLending isn't stagnent, so the model they chose has to be able to adjust with the changing data they feed it. 
* As a result, I would not reccomend this model for finding high risk applicants. 


## Balanced Random Forest Classifier


![Balanced Random Forest Classifier pt 1](https://user-images.githubusercontent.com/100237685/180667563-6ca75f0a-c289-45b2-bd73-b0bdbc55b8ab.png)
![Balanced Random Forest Classifier pt 2](https://user-images.githubusercontent.com/100237685/180667568-9b203a72-33a9-4c48-8b8d-ea229bc9db71.png)
![Balanced Random Forest Classifier pt 3](https://user-images.githubusercontent.com/100237685/180667570-4acdfa50-02f5-4154-a13c-612d3f5e2de0.png)


* hfhf
* jfjf

# Summary
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
