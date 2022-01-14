## Report:Predict Bike Sharing Demand with AutoGluon Solution

Pooja Singari

### Project Instructions
1. Create an account with Kaggle.
2. Download the Kaggle dataset using the kaggle python library.
3. Train a model using AutoGluon’s Tabular Prediction and submit predictions to Kaggle for ranking(Phase 1)
4. Use Pandas to do some exploratory analysis and create  new features, save new versions of the train and test dataset(Phase 2)
5. Rerun the model and submit the new predictions for ranking.
6. Tune at least 3 different hyperparameters from AutoGluon and resubmit predictions to rank higher on Kaggle(Phase 3)
7. Write up a report on how improvements (or not) were made by either creating additional features or tuning hyperparameters, and which phase according to you was the best approach to invest your time in.

## Initial Model Training:Using AutoGluon’s Tabular Prediction [Phase 1]
**Problems Faced:** Initially I did face a few problems while starting the project as I ended up getting losses as high as ```1.77``` because I had not submitted the
right predictions to kaggle but after figuring out my mistake I was able to train a better model as compared to before.
**Solution:** For Phase 1 of the project the training was done with default parameters without addition of any new features or no hyper-parameter tuning as 
of such which led to a model score of ```1.39```

### Top Ranked Model
 After analysing all the models
 'WeightedEnsemble_L3 ' with a score of '-114.911420' was found to be the best among all of them through fit_summary()
 
## Exploratory data analysis and New feature creation [Phase 2]
**Issues Solved:** I found that certain ways of submitting the result proved to improve my results such as
```
new_predictions[new_predictions<0] = 0
```
 The above mentioned code seemed to give me a better result as opposed to using enumerate() to set negative predictions to zero.
 
 **Data Analysis:** I used histograms to do exploratory analysis which helped me to discover the skewness in the data.Moreover, 
 I found the model that the model performed better
 after adding more features such as ['year','month','day','hour'] and also converting the ['season','weather'] columns into category type.
 ## Model Performance
 After analysing all the models
 'WeightedEnsemble_L3 ' with a score of '-35.109906' was found to be the best among all of them through fit_summary()
 This led to a far better score of ```0.47``` which is 66.18% lower than the previous score of ```1.39``` (model trained without any additional features)
 
 ## Hyper parameter Tuning [Phase 3]
   I chose to tune the hyperparameters of 2 models in particular: NN(neural network with MXNet backend) and GBM(LightGBM)
  
 ### Hyper-parameters tuned:

* NN:
  * epochs- I found 11 to be optimal for the task   ***as a higher value seemed to lead to overfitting***
  * activation functions-['relu', 'softrelu', 'tanh'] were chosen as the ***categorical hyper-parameters to tune***
  
* GBM:
  * num_boost_round-127  ***a value >127 should enable the model to perform better***
  * num_leaves(lower=25, upper=58)  ***value <58 for upper seemes to undertrain the model***
     
     
 **Future Work:** I believe that given more time the hyper-parameters can be fine-tuned to ensure that the model performs better while
 adhering to the respective observations mentioned for each parameter.
 ![image](https://user-images.githubusercontent.com/97392797/149452396-c51df957-cbf2-4f00-bdbe-bf96660bda21.png)

### Model Performance
After analysing all the models
 'WeightedEnsemble_L3 ' with a score of '-40.428874' was found to be the best among all of them through fit_summary()
 This led to a score of ```0.48``` which was pretty close to the score of ```0.47``` recieved from adding additional features, a better
 score can be obtained by further tuning the parameters.
 
### Plot:Models vs kaggle score
<img src="https://user-images.githubusercontent.com/97392797/149315694-27932caf-998d-4789-be8a-dbec57286335.png" width="600" height="450">
### Plot: Improvement in kaggle scores (raw submission,additional features,hyper-parameter tuning)
<img src="https://user-images.githubusercontent.com/97392797/149315922-4d32015d-a47f-4fa6-b450-cec99abe7316.png" width="600" height="450">

## Conclusion
I found that Exploratory Data Analysis(EDA) helped me understand the data in a better manner.In the future I would like to experiment to see
how the model would perform with the combined effect of **Phase 2** and **Phase 3** by adding more features such as working time and
seasonal fluctuations along with tuning the hyper-paramters according to the observations made above.


