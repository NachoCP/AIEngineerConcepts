# Quadratic Discriminant Analysis (QDA)

Quadratic Discriminant Analysis (QDA) is a classification technique that extends Linear Discriminant 
Analysis (LDA) by allowing for nonlinear separation of data. 
While LDA assumes that different classes share the same covariance matrix, 
QDA relaxes this assumption, allowing each class to have its own covariance matrix. 
This flexibility enables QDA to capture more complex boundaries between classes than LDA.

## Conceptual Foundations

The key difference between LDA and QDA lies in their assumptions about the covariance matrices:

- **LDA** assumes homogeneity of covariance matrices across classes. This leads to linear decision boundaries.
- **QDA** allows each class to have its own covariance matrix, resulting in quadratic decision boundaries that can adapt to the specific spread of each class.

The decision boundaries in QDA are quadratic, which means they can be curves (ellipses, parabolas, hyperbolas) rather than straight lines or planes. This characteristic makes QDA suitable for datasets where the separation between classes is not linearly describable.

## How QDA Works

1. **Class-Specific Covariance Matrices**: QDA computes a covariance matrix for each class separately. These matrices capture how features vary together within each class, allowing for the modeling of the unique shape of each class distribution.

2. **Quadratic Discriminant Function**: For each class, QDA defines a discriminant function that is quadratic in nature. The classification decision is based on which class's discriminant function yields the highest value for a given observation.

3. **Estimation of Parameters**: QDA estimates the parameters of the Gaussian distributions (means and covariance matrices) for each class. The estimation is usually done using maximum likelihood estimation, similar to LDA.

4. **Prediction**: Given a new observation, QDA calculates the discriminant score for each class using the observation’s features. The observation is then assigned to the class with the highest score, taking into account the quadratic nature of the boundaries.

## Assumptions and Limitations

- **Assumptions**: Like LDA, QDA assumes that the data for each class follows a multivariate normal distribution. However, unlike LDA, it does not require the covariance matrices of these distributions to be identical across classes.

- **Limitations**: The flexibility of QDA comes at the cost of increased computational complexity and the need for more data to estimate the parameters accurately, especially as the number of features grows. With a separate covariance matrix for each class, QDA can quickly run into the problem of overfitting, especially in high-dimensional spaces with limited training data.

## Practical Considerations

- **Model Complexity**: QDA's allowance for class-specific covariance matrices increases model complexity, making it more prone to overfitting compared to LDA. Regularization techniques or dimensionality reduction before applying QDA can help mitigate this risk.
- **Data Requirements**: Due to its increased complexity, QDA requires more data to accurately estimate the covariance matrices. In cases where data is limited, LDA or regularized versions of QDA might be more appropriate.
- **Decision Boundary Flexibility**: The ability of QDA to model quadratic decision boundaries makes it suitable for datasets where classes are not linearly separable. It can capture more complex relationships in the data compared to LDA.

## Summary

QDA is a powerful classification technique that can model complex relationships between features and classes by allowing nonlinear 
decision boundaries. While it offers greater flexibility than LDA, it also requires careful consideration regarding overfitting and 
the sufficiency of training data. In scenarios where classes exhibit significantly different covariance structures, 
QDA can significantly outperform LDA and other linear models.