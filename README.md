# Matrix Completion Algorithms for MovieLens Dataset

Authors:
- Cellitti Francesco
- Negroni Edoardo

This repository contains an implementation of various matrix completion algorithms using the MovieLens dataset. The primary focus is on collaborative filtering techniques to predict missing ratings based on observed data. Specifically, we will be working with the following algorithms:

- **Singular Value Projection** (SVP)
- **Singular Value Thresholding** (SVT)
- **Alternating Direction Method of Multipliers** (ADMiRA)
## Overview
Collaborative filtering is a popular method used in recommender systems, where the goal is to predict a user's preferences based on the preferences of others. The MovieLens dataset is often used for benchmarking collaborative filtering methods. The dataset contains user ratings for movies, where each row represents a rating provided by a user for a particular movie.

In matrix completion, the goal is to infer the missing values (ratings) from the observed entries, which is a low-rank approximation problem. This repository provides an implementation of three matrix completion techniques designed to fill in the missing ratings based on available ones.

## Algorithms Implemented
- **Singular Value Projection (SVP)**: This method projects the observed data onto the space spanned by the singular vectors of the matrix and solves for the missing entries.
- **Singular Value Thresholding (SVT)**: SVT approaches the matrix completion problem by solving a convex optimization problem, where the matrix is approximated by a low-rank matrix that minimizes the nuclear norm.
- **Alternating Direction Method of Multipliers (ADMiRA)**: ADMiRA is a more advanced algorithm that alternates between updating two variables (the matrix and the auxiliary variable) using a method that combines augmented Lagrangian techniques with alternating minimization.

- This repository implements three matrix recovery algorithms—SVP, SVT, and ADMiRA—for low-rank matrix approximation, which can be used for tasks like matrix completion and dimensionality reduction.

### 1. SVP (Singular Value Projection)
The SVP algorithm approximates the low-rank matrix by thresholding its singular values, aiming to minimize the rank and error. We apply cross-validation to determine the optimal regularization parameter (lambda).

- Key Results:
  - RMSE: 1.152
  - Time: 19.64 minutes
  - Iterations: 42
### 2. SVT (Singular Value Thresholding)
SVT is another low-rank matrix approximation method. Cross-validation is used to select an optimal lambda parameter, balancing the trade-off between rank minimization and error reduction.

- Key Results:
  - RMSE: 1.625
  - Time: 9.95 minutes
  - Iterations: 23
### 3. ADMiRA (Atomic Decomposition for Minimum Rank Approximation)
ADMiRA is an efficient algorithm for matrix recovery that uses atomic decomposition. It aims to approximate the matrix with the minimum rank while maintaining accuracy.

- Key Results:
  - RMSE: 1.101
  - Time: 3.52 minutes
  - Iterations: 48
## Results Comparison

| Algorithm | RMSE  | Computational Time (min) | Number of Iterations |
|-----------|-------|--------------------------|----------------------|
| SVP       | 1.152 | 19.64                    | 42                   |
| SVT       | 1.625 | 9.95                     | 23                   |
| ADMiRA    | 1.101 | 3.52                     | 48                   |

## Observations:

- ADMiRA achieves the lowest RMSE and the fastest computation time.
- SVT requires fine-tuning the lambda parameter, which can be computationally intensive.
- SVP has a higher computational time but produces comparable results to ADMiRA in terms of RMSE.
In conclusion, ADMiRA is the most efficient algorithm overall, balancing both low RMSE and quick computation time.

### Visualizations
We also provide visualizations of the matrix recovery progress, showing how the algorithms approximate the original sparse matrix.

