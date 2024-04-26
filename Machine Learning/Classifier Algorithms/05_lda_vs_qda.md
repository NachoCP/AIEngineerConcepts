# Exercise

We now examine the diferences between LDA and QDA.

- (a) If the Bayes decision boundary is linear, do we expect LDA or
QDA to perform better on the training set? On the test set?
- (b) If the Bayes decision boundary is non-linear, do we expect LDA
or QDA to perform better on the training set? On the test set?
4.8 Exercises 195
- (c) In general, as the sample size n increases, do we expect the test
prediction accuracy of QDA relative to LDA to improve, decline,
or be unchanged? Why?
- (d) True or False: Even if the Bayes decision boundary for a given
problem is linear, we will probably achieve a superior test error rate using QDA rather than LDA because QDA is fexible
enough 

## (a) Linear Bayes Decision Boundary
Training Set: When the Bayes decision boundary is linear, LDA is expected to perform better on the training set. This is because LDA assumes a linear decision boundary and a shared covariance matrix across classes, which aligns well with the true nature of the data. QDA, with its allowance for a quadratic boundary and class-specific covariance matrices, may introduce unnecessary complexity, leading to overfitting on the training data.

Test Set: For the test set, LDA is also expected to perform better for the same reasons. The simplicity of LDA’s model, when the true boundary is indeed linear, typically results in better generalization from training data to unseen test data. QDA's additional complexity can harm its predictive performance on the test set due to overfitting.

## (b) Non-linear Bayes Decision Boundary
Training Set: If the Bayes decision boundary is non-linear, QDA is expected to perform better on the training set. QDA's flexibility to model quadratic decision boundaries allows it to more closely fit the true non-linear boundary, compared to LDA's linear approximation.

Test Set: On the test set, the answer is less straightforward and depends on the specific data distribution and the amount of training data available. If the dataset is sufficiently large to mitigate overfitting, QDA can also perform better on the test set due to its ability to capture the true non-linear nature of the decision boundary. However, if the dataset is small, LDA might still perform better on the test set because it's less prone to overfitting, despite the non-linear Bayes boundary.

## (c) Effect of Increasing Sample Size (n) on QDA vs. LDA
As the sample size $n$ increases, the relative test prediction accuracy of QDA compared to LDA is expected to improve. With more data, QDA can more accurately estimate the parameters of the class-specific covariance matrices without as much risk of overfitting. This means that the added flexibility of QDA becomes an advantage rather than a liability, allowing it to potentially capture complex patterns in the data that LDA might miss. This effect is contingent on the true decision boundary being non-linear; if the true boundary remains linear, LDA's performance relative to QDA may not significantly deteriorate even with increased sample size.

## (d) Superiority of QDA over LDA for Linear Bayes Boundary
Statement: Even if the Bayes decision boundary for a given problem is linear, we will probably achieve a superior test error rate using QDA rather than LDA because QDA is flexible enough.

Evaluation: False. When the Bayes decision boundary is linear, introducing the additional flexibility of QDA does not necessarily lead to superior test error rates; in fact, it can lead to the opposite. The increased model complexity of QDA, due to its quadratic decision boundaries and class-specific covariance matrices, is more prone to overfitting, especially with limited training data. In cases where the true decision boundary is linear, LDA's assumption about the linearity and shared covariance structure is more aligned with the true data generation process, often resulting in better generalization to the test set.

In summary, the choice between LDA and QDA should be informed by the nature of the data, particularly the shape of the decision boundary and the amount of training data available. For linear boundaries, LDA's simplicity is typically an asset, while for non-linear boundaries and with sufficient data, QDA's flexibility may provide an advantage.