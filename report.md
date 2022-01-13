## Report:Predict Bike Sharing Demand with AutoGluon Solution

Pooja Singari

### Initial Model Training:Using AutoGluon’s Tabular Prediction
Initially I did face a few problems while starting the project as I ended up getting losses as high as 1.77 but after a few trial and errors
the training was done with default parameters and no hyper-parameter tuning as of such which led to a model score of 1.39

### Top Ranked Model
 After analysing all the models
 'WeightedEnsemble_L3 ' with a score of '-114.911420' was found to be the best among all of them through fit_summary()
 
## Exploratory data analysis and feature creation
 I used histograms to do exploratory analysis which helped me to discover the skewness in the data.Moreover, I found the model that the model performed better
 after adding more features such as ['year','month','day','hour'] and also converting the ['season','weather'] columns into category type.
 ## Model Performance
 After analysing all the models
 'WeightedEnsemble_L3 ' with a score of '-35.109906' was found to be the best among all of them through fit_summary()
 This led to a far better score of 0.47 which is 66.18% lower than the previous score of 1.39 (model trained without any additional features)
 
 ## Hyper parameter Tuning
   I chose to tune the hyperparameters of 2 models in particular: NN(neural network with MXNet backend) and GBM(LightGBM)
  
 ### Hyper-parameters tuned:
 NN: 1.epochs- I found 11 to be optimal for the task ad a higher value seemed to lead to overfitting
     2.activation functions-['relu', 'softrelu', 'tanh']
     
 GBM: 1.num_boost_round-127
      2.num_leaves(lower=25, upper=58) value <58 for upper seemes to undertrain the model
![image](https://user-images.githubusercontent.com/97392797/149315403-f6bfc629-b534-403b-bc57-b5a9f8867c2a.png)

### Model Performance
After analysing all the models
 'WeightedEnsemble_L3 ' with a score of '-40.428874' was found to be the best among all of them through fit_summary()
 This led to a score of 0.48 which was pretty close to the score of 0.47 recieved from adding additional features, a better score can be obtained by further
 tuning the parameters.
 
### Plot:Models vs kaggle score
![image](https://user-images.githubusercontent.com/97392797/149315694-27932caf-998d-4789-be8a-dbec57286335.png)
### Plot: Improvement in kaggle scores (raw submission,additional features,hyper-parameter tuning)
![image](https://user-images.githubusercontent.com/97392797/149315922-4d32015d-a47f-4fa6-b450-cec99abe7316.png)



