# Model order reduction (MOR)

Model order reduction (MOR) is a technique for reducing the computational complexity of mathematical models in numerical simulations. 
As such it is closely related to the concept of metamodeling with applications in all areas of mathematical modelling.

# Principal component analysis

Principal Component Analysis, or PCA, is a dimensionality-reduction method that is often used to reduce the dimensionality of large data sets, by transforming a large set of variables into a smaller one that still contains most of the information in the large set.

Reducing the number of variables of a data set naturally comes at the expense of accuracy, but the trick in dimensionality reduction is to trade a little accuracy for simplicity. Because smaller data sets are easier to explore and visualize and make analyzing data much easier and faster for machine learning algorithms without extraneous variables to process.

In this process of computing the principal components and using them to perform a change of basis on the data, sometimes using only the first few principal components and ignoring the rest.

Principal component analysis (PCA) is usually explained via an eigen-decomposition of the covariance matrix.

Principle components captures the more variance in the data.

![PCA](https://user-images.githubusercontent.com/42026685/106736874-4b165300-6616-11eb-881f-499acf3cb569.gif)

# STEP BY STEP EXPLANATION OF PCA

1. STANDARDIZATION

The aim of this step is to standardize the range of the continuous initial variables so that each one of them contributes equally to the analysis.

Mathematically, this can be done by subtracting the mean and dividing by the standard deviation for each value of each variable.

![std](https://user-images.githubusercontent.com/42026685/106738562-5bc7c880-6618-11eb-9705-0cb28c530ac1.png)

Once the standardization is done, all the variables will be transformed to the same scale.

2. COVARIANCE MATRIX COMPUTATION

The aim of this step is to understand how the variables of the input data set are varying from the mean with respect to each other, or in other words, to see if there is any relationship between them.

The covariance matrix is a p × p symmetric matrix (where p is the number of dimensions) that has as entries the covariances associated with all possible pairs of the initial variables. For example, for a 3-dimensional data set with 3 variables x, y, and z, the covariance matrix is a 3×3 matrix of this from:

![Covariance_matrix](https://user-images.githubusercontent.com/42026685/106738141-df34ea00-6617-11eb-8beb-f5df60b72736.png)

3.  COMPUTE THE EIGENVECTORS AND EIGENVALUES OF THE COVARIANCE MATRIX TO IDENTIFY THE PRINCIPAL COMPONENTS

Eigenvectors and eigenvalues are the linear algebra concepts that we need to compute from the covariance matrix in order to determine the principal components of the data.

# Singular Value Decomposition

Principle component analysis (PCA) can also be performed via singular value decomposition (SVD) of the data matrix X.

In linear algebra, the singular value decomposition (SVD) is a factorization of a real or complex matrix that generalizes the eigendecomposition of a square normal matrix to any m x n matrix via an extension of the polar decomposition.

![svd](https://user-images.githubusercontent.com/42026685/106739286-3f785b80-6619-11eb-9bfc-5f917e3f2067.png)

The SVD can be calculated by calling the svd() function.

Original matrix will be decomposed into 3 matrices. U, S and V transpose. Column vectors of U matrix will contain the eigenvectors of covariance matrix A * A^T. S matrix will be a diagonal matrix and  
contains the singular values, and V^T matirx contains the eigenvectors of coariance matrix A^T * A.

# Reconstruct Matrix from SVD

The approximated matrix with lower rank (r) of the original matrix can be reconstructed by using the first few eigenvectors and eigenvalues from the U, Sigma, and V^T matrices.
