# Causal-Inference-in-Time-Series-Modelling

##### Prediction Task vs Causal Task
In a prediction task, the goal is to predict an outcome Y given a set of features X. Here we only try to approximate a target variable with independent variables which have similar distributional properties. A simple correlation between X and Y can be helpful for these types of predictions.
In a causal task, we want to know how changing an aspect of X affects an outcome Y. In this case, it’s critical to know whether changing X causes an increase in Y, or whether the relationship in the data is merely correlational.

##### Causal Inference in time series
Can we apply methods for forecasting time series to infer the causal impact among the variables?
In most real-world datasets, features are not independent and unconfounded, so standard predictive models will not learn the true causal effects. But sometimes we can fix or at least minimize this problem but only observational causal effects.

##### Bayesian Structural Time Series
BSTS models, employ a probabilistic approach to modelling a time series problem, they return a posterior predictive distribution over which we can sample to provide not only a forecast but also a means of quantifying model uncertainty. Another exciting and highly useful feature of BSTS model is that the resulting model can be decomposed as a collection of separate components.
Definition
The Bayesian structural time-series models are based on two equations, one is the observation equation fitting observed data to a state vector, and the other is a state equation that describes how the state vector evolves over time. For the state itself they use a local linear trend, which is good for short term predictions, combined with a seasonality model where appropriate. 
Eq 1: observation equation: This links the observed data y_t to a latent d-dimensional state vector, α_t.

y_t=z_t^T α_t+ βX_t+G_t ϵ_t

Eq 2: state equation: it governs the evolution of the state vector α_t through time. 

α_(t+1)=T_t α_t+ R_t η_t

α variable refers to the “state” of the time-series, and y_t is a linear combination of the states, plus a linear regression with some explanatory covariates, X, plus noise ϵ, that is normally distributed.
ϵ_t and η_t are independent of all other unknowns.

ϵ_t~ N(0,σ_t^2 )

η_t~ N(0,Q_t )

##### Google’s Causal Impact Model:
Luckily you don’t have to explicitly decompose any of the model’s structural components defined above, google has introduced a package for causal inferencing in time series models in 2016, which they first presented it in “Big data Spain Conference”.
Its main purpose is to identify and measure the effect of some event which change the course of the time series of interest.
It forecasts by fitting a Bayesian Structural time series model to observed data which later used for predicting what the results would have been if the intervention did not happen (counterfactual explanation). It then calculates the cumulative difference between the forecasted and actual values to determine the incremental lift of the event.

