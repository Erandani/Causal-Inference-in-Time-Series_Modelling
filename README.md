# Causal-Inference-in-Time-Series-Modelling

Although predictions of future events are necessarily uncertain, forecasting is a critical part of planning for the future.Methods for forecasting time series can also be applied to infer the causal impact of a feature launch or other intervention.

#### Structural Time Series
Structural time series (STS) models are a family of probability models for time series that includes and generalizes many standard time-series modeling ideas, including:

autoregressive processes,
moving averages,
local linear trends,
seasonality, and
regression and variable selection on external covariates (other time series potentially related to the series of interest).

An STS model expresses an observed time series as the sum of simpler components:
f(t)=f_1 (t)+f_2 (t)+⋯+f_n (t)+ε; ε~N(0,σ^2)

The individual components are each time series governed by a particular structural assumption. For example, one component might encode a seasonal effect (e.g., day-of-week effects), another a local linear trend, and another a linear dependence on some set of covariate time series.
