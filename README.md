# Tree_Survival

<ins>Technologies and Libraries</ins>    
* Python
* Pandas
* Lazypredict
* Sklearn
* Lightgbm

In this project, I wanted to simply create a supervised learning model that could predict a tree's death based on the features given. The model used for this project was LGBMClassifier.    

Before the model was decided, I first had to clean the data. I removed several columns that either had too many null values or were simply a label to identify the single tree-like id. Then I converted any non-integer/float column into a number value. I then checked the correlation of all columns and noted those that could be removed. Once that was all done, I trained the data through Lazypredict to see which models performed the best. I decided from there to use the LGBMClassifier for the rest of the project.    

## Creating the Model
To get the result I did, several attempts were made to produce a better model. One of these ways was to remove all the columns that were 5% away from 0. That caused the model to perform worse, which I assume was because some of the columns were important for the ones kept in predictions. It did the best when only removing a single column, being the Subplot. It slightly improved the model score by roughly 0.2%.    
The next way I attempted to improve the model was through fine-tuning the parameters. These attempts bear no fruit since increasing/decreasing by any amount either didn't affect the model or worsened it. That led me to leave it to the default parameters.    
The last way was using the date column to see if the month the tree was planted affected the result. To my surprise, it didn't affect the result at all. I was puzzled, but the result speaks for themselves. I then decided to leave the plant date out.   
In the end, I was left with a model with no changed parameters, one column removed(excluding those removed earlier), and no additional features added. The model ended with an accuracy score of 97.7%.    

## Visuals
![Capture](https://github.com/Cabone01/Tree_Survival/assets/89541481/19b5d826-d29c-4985-a726-c1f0c5d1ad6d)    
This graph shows the model performed by showing how many were guessed wrong and correctly. We can see that it correctly predicted 283 dead trees and 397 living trees. However, it made mistakes by saying 11 trees were alive when it was dead, and 5 trees were dead when it was alive.    

## References
Dataset Link: https://www.kaggle.com/datasets/yekenot/tree-survival-prediction 

