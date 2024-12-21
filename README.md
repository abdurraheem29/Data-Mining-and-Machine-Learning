# Data-Mining-and-Machine-Learning
Key Tasks
1. Subset Selection
Task: How many different possible subsets of inputs (including the empty subset) can be used for prediction?
2. Best Subsets Algorithm
Method: Use the leaps::regsubsets function to implement the best subsets algorithm on the training data.

The criterion used for model selection is the Residual Sum of Squares (RSS).
Use BIC (Bayesian Information Criterion) for the final model selection step.
Steps:

Perform the best subsets regression on the data.
Generate two plots:
BIC vs Model Complexity
Mallow’s CP vs Model Complexity
Report the best model for each plot.
3. BIC vs CP Comparison
Task: Compare BIC and Mallow's CP to determine which one selects a larger or smaller model.
Explanation: Discuss how BIC and CP behave in model selection and provide an explanation based on your findings.
4. Validation Set Approach
Task: Use a validation set approach for model evaluation.

Split the data into training (75%) and validation (25%) sets.
Fit all 2^k - 1 models (excluding the null model) using the regsubsets function.
Calculate Model Size, Training MSE, and Validation MSE for each model.
Steps:

Fit all models and compute performance metrics.

Create plots:

Validation MSE vs Model Size
Training MSE vs Model Size
Add lines to the plot indicating the best models according to both prediction MSE and training MSE.
Add a legend for clarity.
Determine the best subset of inputs based on prediction MSE from the validation set.

Data Preprocessing
The dataset is divided into training and validation sets:

R
Copy code
# Split data into training and validation sets
ntot <- nrow(ozone)
ntrain <- round(ntot * 0.75)
nval <- ntot - ntrain

set.seed(20500 + 5150)
trainidx <- sample(1:ntot, size=ntrain, replace=FALSE)
train.df <- ozone[trainidx,]
val.df <- ozone[-trainidx,]
Solution Methodology
Best Subsets Regression
The best subsets algorithm was applied using the leaps::regsubsets function. For model evaluation, we used BIC and Mallow’s CP to select the best models. The code for running the algorithm and generating the plots is included in the repository.

Validation Approach
For the validation set approach, the training data was used to fit all possible models. The performance was evaluated based on training MSE and validation MSE. Models were plotted for both metrics to identify the best subset of features.


