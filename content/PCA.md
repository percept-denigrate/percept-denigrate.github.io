PCA (principal component analysis) is a dimensionality reduction algorithm.

Data is linearly transformed, and expressed with a new coordinate system of orthogonal components. Those components express the most variance and no covariance between one another.

![](https://upload.wikimedia.org/wikipedia/commons/f/f5/GaussianScatterPCA.svg)

Data is then often represented on a 2D graph using the first two principal components.

It is done by centering the data and decomposing the covariance matrix. Each eigenvector is a component, and its eigenvalue is the variance explained by that component.
