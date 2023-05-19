# Parametric Point Estimation

## Introduction

Let's study the theory of point estimation. Suppose, for example, that a random variable $X$ is known to have a normal distribution $\mathcal{N}(\mu,\sigma^2)$, but we do not know one of the parameters, say $\mu$. Suppose further that a sample $X_1, X_2,.. , X_n$ is taken on $X$. The problem of point estimation is to pick a (one-dimensional) statistic $T(X_1, X_2,.. , X_n)$ that best estimates the parameter $\mu$. The numerical value of $T$ when the realization is $x_1, x_2,.. ,x_n$ is called an **estimate** of $\mu$, while the statistic $T = (U, V)$ as an **estimator** of $(\mu, \sigma^2)$.

## Problem of point estimation

Let $X$ be a RV defined on a probability space $(\Omega, \mathcal{S}, \mathcal{P})$. Suppose that the distribution function $F$ of $X$ depends on a certain number of parameters, and suppose the functional form of $F$ is known except perhaps for a finite number of these parameters. Let $\mathbf{\theta} = (\theta_1, \theta_2,..., \theta_k)$ be the unknown parameter associated with $F$.

**Definition 1.** The set of all admissible values of the parameters of a distribution function (DF) is called the parameter space.

## Z-test

Z-test means the following:
Null (H0) and Aternate hypothesis (H1) are defined along with the required significance level to reject H0 or not reject H0. We calculate the observed p-values, and if its smaller than significance level we reject H0.

