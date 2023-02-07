---
title: "Simulations in R"
teaching: 2
exercises: 5
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I make my own data in R?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Learn to use the random number generators in R to simulate data.

::::::::::::::::::::::::::::::::::::::::::::::::



Here's a short interlude on random numbers in R, which you can use to simulate your own data. This can be very useful to set up toy models and see what the data or certain plots would look like in theory.  

For example, we could simulate frog counts from 100 binomial experiments, that is the counts of light colored frogs from filling a net one hundred times:


```r
set.seed(85)
size = 10 # number of frogs per net
prob = 0.3 # true percentage of light colored frogs
n = 100 # number of binomial experiments
binomial_frog_counts <- rbinom(n=n, size=size, prob=prob)
head(binomial_frog_counts)
```

```{.output}
[1] 3 1 2 3 3 4
```

Here, we used `set.seed()` for reproducibility: The seed gives an initialization to the process of drawing random numbers. So any time we run the same simulation with the same seed, we will get the same random numbers. If we don't set the seed, the random numbers will look different each time we run the code.   


::::::::::::::::: challenge
## Poisson random numbers

1. Simulate 100 random frog counts with a Poisson rate of 4. 
2. Calculate the mean of the frog count.

::::::::::::::::: solution

```r
set.seed(81)
# 1. simulation
frog_counts <-rpois(n = 200, lambda = 4)

# 2. calculate the mean
mean(frog_counts)
```

```{.output}
[1] 3.955
```
:::::::::::::::::::::::::
::::::::::::::::::::::::::::

