
# Model Metrics

- **Dependent Variable**: The variable you are trying to predict or explain. Its behavior is analyzed in relation to independent variables.

- **R-squared**: A measure of how well the independent variables explain the variability in the dependent variable. Values range from 0 to 1, with higher values indicating a better fit. A high R-squared does not necessarily mean the model is good; it must be interpreted in the context of the research question and other diagnostics.

- **Adjusted R-squared**: Adjusts the R-squared for the number of predictors in the model. It penalizes for adding predictors that do not improve the model significantly. A value closer to R-squared suggests minimal penalty for unnecessary predictors.

- **F-statistic**: Tests the overall significance of the model. A higher F-statistic indicates a more significant predictive capability of the model as a whole.

- **Prob (F-statistic)**: The p-value corresponding to the F-statistic. A small p-value (typically <0.05) suggests that at least one of the predictors is significantly related to the dependent variable.

## Regression Coefficients

- **Intercept**: The expected value of the dependent variable when all independent variables are zero. Its significance indicates whether this expected value is significantly different from zero.

- **Coefficient** (for each predictor): Represents the change in the dependent variable for a one-unit change in the predictor, holding other variables constant. A positive coefficient suggests a direct relationship, while a negative coefficient suggests an inverse relationship with the dependent variable.

- **Standard Erro**r (of the coefficient): Measures the variability of the coefficient estimate. A smaller standard error suggests a more precise estimate.

- **t-statistic**: Used to determine the significance of individual regression coefficients. Higher absolute values suggest greater significance.

- **$P>|t|$**: The p-value associated with the t-statistic for each predictor. A small p-value indicates that the predictor is a significant determinant of the dependent variable, considering other factors in the model.

## Diagnostic Tests

- **Omnibus**: Tests the null hypothesis that residuals are normally distributed. A significant test suggests non-normality.

- **Prob(Omnibus)**: The p-value for the Omnibus test. A value close to 0 suggests the residuals do not follow a normal distribution.

- **Durbin-Watson**: Tests for autocorrelation in the residuals. Values close to 2 suggest no autocorrelation, while values deviating from 2 indicate positive or negative autocorrelation.

- **Jarque-Bera (JB)**: Another test for normality of residuals. Significant values indicate deviation from normality.

- **Skew**: Measures the asymmetry of the residual distribution. Values far from 0 indicate asymmetry.

- **Kurtosis**: Measures the tailedness of the residual distribution. Values far from 3 suggest either flatter or more peaked distributions than the normal distribution.

- **Cond. No.** (Condition Number): Assesses the multicollinearity among predictors. High values indicate a high degree of multicollinearity, which can make the model unstable and coefficients unreliable.

