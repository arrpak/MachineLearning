# Feature Selection (Dimensionality Reduction)
## Why?
- Removing irrelevant features results in:
    - a better performing model 
    - a model that runs faster
    - a easier to understand model
## How?
1. Percent missing values
2. Amount of variation
3. Pairwise correlation
4. Multicolinearity
5. Principal Component Analysis PCA
6. Cluster Analysis
7. Correlation (with the target)
8. Forward Selection
9. Backward elimination RFE
10. Stepwise Selection
11. LASSO
12. Tree-based selection


### 1.Percent missing values
- Drop features that have a very high % of missing values
    - Number of records with missing values/ number of records
- Or Create binary indicators to denote missing (or non-missing) values
- Review or visualize features with high % of missing values
### 2.Amount of Variation
- Drop or review features that have very low variation
    - $VAR(x)=σ^{ 2 }=1/n∑_{ i }^{ n }(x_{ i }-μ)^{ 2 }$
    - Either standardize all features, or use standard deviation to account for variables with difference scales
    - Drop variables with zero variation
### 3.Pairwise Correlations
- Many features are often correlated with each other, and hence are redundant
- If two variables are highly correlated, keeping only one will help reduce dimensionality without much loss of information
- What feature to keep? The one that has higher correlation coeff with the Target

![img](https://github.com/emunozlorenzo/Machine-Learning-Course/blob/master/img/img3.jpg)
 

### 4.Multicolinearity
- When two or more features are highly correlated each other
- Dropping one or more features will help reduce dimensionality without much loss of information
- What feature to keep?  Use CONDITION INDEX or VIF

![img](https://github.com/emunozlorenzo/Machine-Learning-Course/blob/master/img/img2.jpg)

### 5.PCA
- Dimensionality reduction technique which emphasizes variation
- Eliminates multicolinearity. But explicability os compromised
    - Uses orthogonal transformation
- When to use:
    - Excessive multicolinearity
    - Explanation of the predictors is not important
    - A slight overhead in implementation is ok
    - More suitable for unsupervised learning
### 6.Cluster Analysis
- Dimensionality reduction technique which emphasizes correlation/similarity
    - Identify groups of features that are as correlated as possible among themselves and as uncorrelated as possible with variables in other clusters
- Reduces multicolinearity. And explicability is not (always) compromised
- When to use:
    - Excessive multicolinearity
    - Explanation of the predictors is important
### 7.Correlation with the Target
- Drop variables that have very low correlation with the target
    - If the feature has a very low correlation with the targe, it’s not going to be useful for the model prediction
- Careful: you could miss a useful feature because 
    - feature A does not correlate with the target
    - feature B does not correlate with the target
    - BUT feature A and B together are correlated with the target

### 8.Forward Selection
- Identify the best variable (ex: based on model accuracy)
- Add the next best variable into the model
- And so on until some predefined criteria is satisfied
- We can see p-value (feature) AIC R2 adjusted F-stat prob(F-stat)…
### 9.Backward Selection
- Start with all variables included in the model
- Drop the least useful feature( based on p-value)
- And so on until some predefined criteria is satisfied
- We can see p-value (feature) AIC R2 adjusted F-stat prob(F-stat)…
### 10.Stepwise Selection
- Similar to forward selection process, but a feature can also be dropped if that feature is not useful anymore after a certain number of steps

[MLXTEND](http://rasbt.github.io/mlxtend/user_guide/feature_selection/SequentialFeatureSelector/)

[Feature Selection Scikit Learn](https://scikit-learn.org/stable/modules/feature_selection.html)

### 11.LASSO or RIDGE (Linear Models)
- Least Absolute Shrinkage and Selection Operator LASSO
- Two birds, one stone: FEATURE SELECTION + REGULARIZATION

### 12.Tree-based
- Forests of trees to evaluate the importance of features
- Fit a number of randomized decision trees on various sub-samples of the dataset and use averaging to rank order features

![img](https://github.com/emunozlorenzo/Machine-Learning-Course/blob/master/img/img1.jpg)
