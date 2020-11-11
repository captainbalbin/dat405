# Lecture 2 - Regression

[Lecture Slides](https://chalmers.instructure.com/courses/10918/files/894149?module_item_id=127122) |
[Edureka Video](https://www.youtube.com/watch?v=E5RjzSK0fvY) |
[Deepnote Project](https://deepnote.com/project/4c0f7cb7-b163-414e-9909-976f6d9a1b0d#%2Fnotebook.ipynb)

## What is Regression?

Graphing a line over a set of data points that most closely fits the overall shape of the data.

## Linear vs. Logistic

| Basis                        | Linear                                               | Logistic                                                                                |
| ---------------------------- | ---------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Core concept                 | Data is modelled using a straight line               | Probability is represented as a linear function of a combination of predictor variables |
| Used with                    | Continuous variable                                  | Categorical variable                                                                    |
| Output/Prediction            | Value of the variable                                | Probability of occurence of event                                                       |
| Accuracy and Goodness of fit | Measured by loss, R squared, adjusted R squared etc. | Accuracy, precision, recall, ROC curve etc.                                             |

## Linear Regression

### _Selection Criteria_

**Classification and regression capabilities**

Predicts a continoul model by fitting a line

**Data quality**

Each missing value removes a datapoint that could optimise the regression.
Outliers can disturb the outcome

**Computational complexity**

Usually cheap

**Comprehensible and Transparent**

Can be represented by a simple mathematical notation.

### _Where is it used?_

**Evaluate trends and sales estimates**

Can used the slope of the regression line to forecast future outcomes.

**Analyzing the impact of price changes**

Can help with future pricing predictions.

### Linear Regression Algorithm

![linear regression](https://i.gyazo.com/d0c883d13a20537d36752e7bca93cdf6.png)

## Predicting

**Regression**: Predicting a numerical quantity

**Classification:** Assigning a label from a discrete set of possibilies

**Clustering:** Grouping items by similarities

## Linear Regression

Base on previous known variables and draw a line through them. We want to be able to fit a line `f(x) = kx + m`.

### Measure Errors

Measure error of the line as the sum of squared error of the datapoints

## Rediduals
