---
title: 'Exercises'
teaching: 0
exercises: 90
---

## Exercises

Here are some exercises for you to try yourself out in R, to practice your knowledge on probability distributions, and to construct and interpret meaningful visualizations.  

Please feel encouraged to work in RStudio on your own computer for this! This way, you will have an installation and some scripts ready once you decide to work on your own data.  

To install all packages necessary for completing the exercises and running the examples in this tutorial, run the following command on your computer:


```r
source("https://www.huber.embl.de/users/kaspar/biostat_2021/install_packages_biostat.R")
```


### The `discoveries` data

Consider the `discoveries` data. This data set is contained in base R and has the number of "great inventions" for a number of years. These are clearly count data. 



1. Look up the example data using the R `help` function.  
2. Compare the fit to a Poisson with a fit to a negative binomial (=gamma poisson) distribution.  
3. Which of the two distribution do you think describe the data better? And what could be a reason for that (remember what the data describe)?  
4. What could be problematic about fitting a Poisson or negative binomial distribution to these data? Which assumption could be violated?  


```r
discov <-  discoveries[1:100]
library(vcd)
```

```{.output}
Loading required package: grid
```


### ELISA example

This example is modified from [chapter 1](https://www.huber.embl.de/msmb/Chap-Generative.html) in MSMB by Susan Holmes and Wolfgang Huber.

When testing certain pharmaceutical compounds, it is important to detect proteins that provoke an allergic reaction. The molecular sites that are responsible for such reactions are called epitopes. 

ELISA assays are used to detect specific epitopes at different positions along a protein. The protein is tested at 100 different positions, supposed to be independent. For each patient, this position can either be a hit, or not.
We’re going to study the data for 50 patients tallied at each of the 100 positions.

Start with the following lines:

```r
epitope_data <- data.frame(position=1:100,
                           count=c(2, 0, 1, 0, 0, 0, 2, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 0, 0, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 1, 1, 0, 1, 2, 2, 7, 1, 0, 2, 0, 1, 0, 1, 1, 1, 1, 0, 1, 0, 0, 0, 0, 1, 2, 2, 1, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 0, 0, 1, 1, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 1, 1, 0, 0, 1, 1, 0, 0, 1, 0))
```
In this data frame, the number of hits among the 50 patients is counted at each position.


1. Plot the data in a meaningful way.  
2. Fit the counts to a Poisson distribution. What is the fitted rate parameter?  
3. Does this look like a good fit?  
4. ELISAs can give false positives at a certain rate. False positive means declaring a hit – we think we have an epitope – when there is none. Assume that most of the positions actually don't contain an epitope. In this case, you can consider the fitted Poisson model as the "background noise" model, with lambda giving the expected number of false positives. Given this model, what are the chances of seeing a value as large as 7, if no epitope is present?


### Mice data

Load the mice data:

```r
mice_pheno <- read_csv(file= url("https://raw.githubusercontent.com/genomicsclass/dagdata/master/inst/extdata/mice_pheno.csv"))
```

1. Plot a histogram, and a normal-QQ plot for female control mice. Would you say the weights follow a normal distribution?
2. For comparing the control and high-fat group (for female mice), show the ECDF of both in the same plot.

