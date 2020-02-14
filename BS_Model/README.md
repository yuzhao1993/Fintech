# clear memory
rm(list=ls())

# Input data X (3 observations, 2 variables)
# each row is an observation
# each column is a variable
X <- matrix(c(1,2,3,4,5,6),3,2, byrow=TRUE)
X

# compute data mean
X_mean <- colMeans(X)
X_mean

# create a data mean matrix: each row is mean
n <- dim(X)[1] # n is number of observations
X_m <- t(matrix(rep(X_mean,n), ncol=n))
X_m

# Adjust the original data by this mean matrix
X0 <- X-X_m
X0

# Compute covariance matrix
C <- t(X0)%*%X0/(n-1)
C

# get eigenvalues and eigenvectors
eigen(C)