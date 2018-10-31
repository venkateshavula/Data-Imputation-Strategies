# Data-Imputation-Strategies
Conventional mean/median imputation is very inaccurate, so we need to explore more scientific methods to impute missing values in longitudinal and temporal data especially applicable to Health care.

Currently there are many data imputation strategies available, but I believe they can be broadly divided into 2-categories(although a combination of stats and ML is used intermittently in all the methods): -

### 1) Statistical-based methods:-

#### Mean: 
Conventional average value imputation. R-library(Hmisc) could also be used to replace a missing value with a constant value. Hmisc has several functions, such as argImpute, to perform multiple imputation using bootstraping and predictive mean matching.

#### Hot Deck: 
a missing value is imputed from a randomly selected "similar" record
#### MF(Matrix Factorization): 
factorize the data matrix into two low-rank matrices, and fill the missing values by matrix completion
#### Amelia: 
uses bootstrapping and Expectation-Maximization algorithm, to impute the missing values in a data set
#### MVNI(Multivariate Normal Imputation): 
MVNI assumes that all variables in the imputation model jointly follow a multivariate normal distribution. Implementation uses a Bayesian approach (with a Markov chain Monte Carlo algorithm) to obtain imputed values from the estimated multivariate normal distribution, allowing appropriately for uncertainty in the estimated model parameters, as required for “proper” imputation
#### MICE(Multiple Imputation by Chained Equations): 
Also known as FCS(Fully Conditional Specification). MICE creates multiple imputations with chained equations
#### Impute TS: 
utilizes the state space model and kalman smoothing.This method is solely dedicated to univariate time series imputation.
#### STMVL: 
utilizes the geo-locations when imputing missing values

### 2) Machine Learning-based methods:-

#### MLP(Multi-layer Perceptron): 
is a neural network can be used to estimate missing values by training an MLP to learn the incomplete features (used as outputs), and using the remaining complete features as inputs
#### SOM(Self-organisation maps): 
is a neural network model and incomplete data is imputed by the feature values of the best matching unit in the missing dimensions.
#### KNN(K-nearest neighbours): 
This algorithm finds the similar samples, and impute the missing values with weighted average of its neighbors
#### GRU-D(Gated-recurrent Unit): 
a recurrent neural network. It takes two representations of missing patterns, i.e., masking and time interval, and effectively incorporates them into a deep model architecture so that it not only captures the long-term temporal dependencies in time series, but also utilizes the missing patterns to achieve better prediction results.
#### BRITS(Bidirectional Recurrent Imputation for Time Series): 
An RNN-based approach directly learns the missing values in a bi-directional recurrent dynamical system, without any specific assumption.
