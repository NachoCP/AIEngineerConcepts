# Multiple Linear Regression

Multiple linear regression extends the simple linear regression model to accommodate more than one predictor variable. This extension is crucial when you suspect that other variables, in addition to the primary predictor, influence the response. Let’s explore this concept with the context of advertising data, where you might not only spend on TV advertising but also on radio and newspapers.

## Motivation for Multiple Linear Regression

Imagine you've analyzed sales data relative to TV advertising spend. However, you also have budget data for radio and newspaper advertising. Analyzing each advertising medium's effect on sales separately through simple linear regressions might lead you to question how these media combined can affect sales. 

Running separate models for each predictor does not allow for a unified prediction of sales considering all advertising mediums together and ignores the possibility that the effectiveness of one medium might depend on the spending on others.

## Multiple Linear Regression Model

The model for multiple linear regression when you have $p$ distinct predictors looks like this:

$Y = \beta_0 + \beta_1X_1 + \beta_2X_2 + ... + \beta_pX_p + \epsilon$

Each $X_j$ represents a different predictor, and each coefficient $\beta_j$ quantifies the expected change in $Y$  for a unit increase in $X_j$, holding all other predictors constant. This model is powerful as it allows for the interaction between multiple predictors and the response.

## Estimating the Coefficients

Just like in simple linear regression, we don't know the true values of the coefficients and must estimate them. This estimation is done through the same least squares principle, aiming to minimize the sum of the squared differences between observed and predicted values. 

However, with multiple predictors, the estimation of these coefficients becomes mathematically more complex, usually requiring statistical software for computation.

## Interpretation in the Advertising Example

In a model incorporating TV, radio, and newspaper advertising as predictors for sales, you might find that while TV and radio advertising have significant positive coefficients, newspaper advertising does not. 

This difference could indicate that spending on newspaper advertising does not contribute to sales once TV and radio spending are accounted for. Such an outcome might suggest reallocating budget from newspapers to radio or TV to maximize sales.

## The Role of Correlation Among Predictors

An interesting aspect of multiple linear regression is how it deals with predictors that are correlated with each other, known as multicollinearity. 

For instance, if radio and newspaper advertising budgets tend to increase together across different markets, a simple regression might misleadingly attribute a change in sales to both when, in fact, only one of them has a real effect. Multiple regression helps untangle these effects by considering them simultaneously.

## Important Considerations in Multiple Regression

- **Model Fit**: The quality of a multiple regression model can be assessed using $R^2$, the proportion of variance in the response variable that is predictable from the predictors. However, unlike simple regression, adding more predictors to a multiple regression model will always increase $R^2$, potentially leading to overfitting. Adjusted $R^2$ and other metrics like AIC and BIC can help compare models with different numbers of predictors.
- **Variable Selection**: Identifying which predictors are genuinely important and which can be omitted without significantly reducing model accuracy is a key challenge. Techniques like forward selection, backward elimination, and mixed selection can help systematically search for a good model.

### Forward Selection

**Forward selection** starts with the most simplified model — excluding all predictors — and adds them one by one. For each step, it considers adding each of the variables not already in the model and selects the variable that results in the greatest improvement to the model fit (often assessed by a metric like the Akaike Information Criterion (AIC) or the p-value associated with the F-statistic of the model). This process is repeated until adding a new variable does not significantly improve the model.

- **Pros**: It is computationally efficient, especially when the number of predictors is large.
- **Cons**: There's a risk of missing the global optimum because once a variable is added, it is not removed if it becomes redundant with later additions.

### Backward Elimination

Backward elimination begins with a full model that includes all potential predictors. Then, it iteratively removes the least useful predictor, one at a time, that has the least statistical significance (e.g., the highest p-value), improving the model fit or reducing information criteria like AIC or BIC. This process continues until removing further variables deteriorates the model based on the chosen metric.

- **Pros**: It considers the full model from the start, which can be advantageous when interaction effects are present.
- **Cons**: It can be computationally expensive with a large number of predictors and may not be feasible if the number of observations is less than the number of predictors.

### Mixed Selection

Mixed selection is a combination of forward selection and backward elimination. It starts like forward selection by adding variables one at a time based on their contribution to the model fit. 

However, after adding a new variable, it checks whether the inclusion of the new variable has made any of the previously included variables statistically insignificant. If so, it removes those variables. This process of adding and potentially removing variables continues until no variables can be added or removed to improve the model.

- **Pros**: It allows for a more flexible model-building process and can more reliably find a good set of predictors.
- **Cons**: It can be more complex and computationally intensive than either forward selection or backward elimination alone.


## Summary
Multiple linear regression is a powerful tool for analyzing the relationship between a response variable and several predictor variables. It provides a more nuanced understanding than simple linear regression, especially in contexts where multiple factors influence the response. However, it requires careful interpretation and validation to ensure that the model accurately represents the underlying data relationships.

## Anexus

### Akaike Information Criterion (AIC)

AIC is based on information theory. The idea behind AIC is to provide a measure of the relative quality of a statistical model for a given set of data. It balances the complexity of the model against how well the model fits the data. A lower AIC value indicates a better model. AIC is calculated using the formula:

$AIC = 2k - 2 \ln(L)$

where

- $k$ is the number of parameters in the model
- $\ln(L) is the natural logarithm of the likelihood fo the model given the data.

AIC encourages model parsimony, meaning that among models with a similar fit, the model with fewer parameters (simpler model) is preferred.

### Bayesian Information Criterion (BIC)

BIC is similar to AIC but introduces a stronger penalty for models with more parameters. It is derived from Bayesian statistics, providing an approximation to the posterior probability of a model being true, under certain assumptions. The formula for BIC is:

$BIC = \ln(n)k - 2\ln(L)$

where:

- $n$ is the number of observations
- $k$ is the number of parameters in the model
- $\ln(L)$ is the natural logarithm of the likelihood of the model given the data.

Because the penalty term for the number of parameters is larger in BIC than in AIC (due to the multiplication by $\ln(n)$), BIC tends to prefer simpler models than AIC, especially as the sample size $n$ grows.

### Comparison and Usage

- **Model Selection**: Both AIC and BIC are used to select models. They are especially useful in situations with a large set of potential models to choose from, such as when performing variable selection in linear regression.
- **Penalizing Complexity**: Both criteria penalize the complexity of the model to avoid overfitting, but BIC tends to penalize complexity more heavily than AIC.
- **Sample Size Sensitivity**: BIC's penalty for the number of parameters increases with the logarithm of the sample size, making it more sensitive to the sample size than AIC. As a result, BIC may prefer simpler models than AIC in cases of large sample sizes.


In practice, the choice between AIC and BIC can depend on the goals of model selection (e.g., prediction accuracy vs. understanding the underlying process) and the sample size. It's not uncommon to consider both criteria and to use them in conjunction with other model evaluation metrics like cross-validation scores or domain-specific considerations.





