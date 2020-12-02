# Lecture 7 - Bayesian

## Bayseian Statistics

**Baye's rule:** `Posterior = Likelihood * Prior / Evidence or marginal likelihood`

### Frequentist vs. Bayesian

#### Frequentist

The probability of an outcome in an experiment, is related to the **frequency** of observing that outcome.

Maximise likeihood function &rarr; point estimate

model (parameters) = data

#### Bayesian

The probability of an outcome in an experiment, is related to our state of **knowledge** _or_ **belief** about the experiemnt.

Simulate posterior distrubution &rarr; probability densitry of parameters

unobserved variables = observed variables

### Bayes Factors

Actually how strong is the evidence? The probability is calculated into bits and after that it can be compared to the Bayes factors's evidence strength.

### Linear Regression with Bayes

**Problem:** Given obeservatioons of two random variables `{x1, x2, ..., xn}, {y1, y2, ..., yn} ~ p(x, y)` we want the regress `y = ax + b`.

### Prior Distributions

Prior distributions can play an important role in Bayesian inference:

- Specify information about the model or model parameters (onubsorved varaiables)
- Regularise likeligoiod funtion &rarr; minimise risk of overfitting

Prior distributions are usually specified before data becomes available. Notable exepections include:

- **Baysian updating**: Updating a previous posterior when new data becomes available. The "old" posterios becomes thew new prior.
- **Emoperical Bayes**: Estimating the priors from data. Approximation of full Bayesian inference in a hierarchical modelm with _Maximal Marginal likelihood_

#### Specifying prior distributions

We just confirm what we want to see. If we fail to take in other information available it's logically inconsistent and economically wasteful.

#### Prior Classes

Every time we specify a prior we're imposing information.
