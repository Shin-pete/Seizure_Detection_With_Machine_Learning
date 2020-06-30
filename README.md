# Seizure Detection With Machine Learning

![Galaxy Brain](https://blueseatblogs.com/wp-content/uploads/2018/07/consciousness-709143-400x300.jpg)

Problem: It can be difficult to determine whether someone has had an epileptic seizure. A misdiagnosis at the beginning can have severe effects where epilepsy, lying untreated, has grave consequences. Sometimes specialists attach EEGs to patients to and use the readings of brain activity ascertain whether someone is having a Epileptic Seizure. I want to see the effect of applying a machine learning algorithm onto the data and examine its efficacy.

[My_notebook](https://nbviewer.jupyter.org/github/Shin-pete/Seizure_Detection_With_Machine_Learning/blob/master/final_model.ipynb)

![Background_img](https://github.com/Shin-pete/Seizure_Detection_With_Machine_Learning/blob/master/5VLnjeD.png?raw=true)

With the background out of the way, we can look at what our data looks like: 

![explore](https://github.com/Shin-pete/Seizure_Detection_With_Machine_Learning/blob/master/AcroRd32_2020-06-30_11-09-40.png)

Unfortunately, our features are anonymized, so there may not be a great deal we can learn from exploring those features. We can still normalize and standardize these features and see how they perform when we run them with our machine learning models. But before we do that we have one final data preprocessing step involves the Y variable. There are 5 different things being captured with this. Seizure activity is being recorded when y is 1. To prepare this portion of the data, we can just run a loop through y and whenever y is not equal to one, set y to 0. Now that our data is prepared, we can split for our testing purposes. 

Import train_test_split from sklearn.model_selection and train the dataset with a test size of .25. Before we get to running any tests, let's check for multicollinearity within the dataset. The heat map below demonstrates that multicollinearity within the dataset is low so Principal Component Analysis is unlikely necessary.

Upon applying a variety of machine learning models, we find that the top two models are Source Vector Machines and Random Forest Classifiers with RF's slightly edging out SVMs. When then perform some gridsearch to help tune our parameters and get our ideal model. 

Now that we have our classifier, let's focus on improving it in another way. For the purpose of this classifier, it's preferable that we are able to identify a seizure when it does happen even if we end up being a bit on the side of over-diagnosing. So, instead of relying on a classifier that says that when it is more than 50% likely to be a seizure, let's make a custom classifier that has a much lower bar for identifying a seizure, say 20% for example. Having done this, we see that we are able to identify an even greater number of seizures, though our precision and accuracy for the model at large decline. 


Refrences: Andrzejak RG, Lehnertz K, Rieke C, Mormann F, David P, Elger CE (2001) Indications of nonlinear deterministic and finite dimensional structures in time series of brain electrical activity: Dependence on recording region and brain state, Phys. Rev. E, 64, 061907

