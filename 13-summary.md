---
title: 'Summary'
teaching: 5
exercises: 0
---



### Sampling and distributions

- In statistics, experiments are viewed as **sampling** processes. Sampling means "drawing events" from a population of interest. If the events are drawn randomly and independently, the results are more likely to give a good representation of reality.  
- A **probability distribution ** assigns probabilities to the possible outcomes (in continuous distributions: to intervals of outcomes).  
- **Discrete** distributions give probabilities for discrete outcomes, for example counts. For **continuous** distributions, every value is assigned a **density**, and probabilities can be calculated by integrating over the density in the interval of interest.  

### Common distributions of biological data

- The **binomial** distribution models the number of successes in a series of trials.  
- The **Poisson** distribution is often used for modeling count data. It assumes that counts were over a fixed volume or period of time. It is an approximation of the binomial distribution.   
- The **negative binomial** distribution is useful for overdispersed count data, that is count data that are poorly fit by Poisson, because they are not collected over fixed domains, or are subject to some additional variation that isn't captured by Poisson.  
- The **Gaussian** or **normal** distribution models repeated measurements of the same thing, and is a continuous distribution. Many distributions (also discrete ones) can be approximated by a Gaussian distribution for sufficiently large sample sizes.   

Confused by what to approximate with what? Here is an overview:

<iframe width="560" height="315" src="https://www.youtube.com/embed/u9onO78hDlw" allowfullscreen></iframe>



### What distribution models your data best?

1. **Fit your data** to a distribution that you consider plausible. The fit gives you the best parameters for this distribution given your data.  
 
2. **Visually compare** the theory (i.e. the fitted distribution) to your data points. A good fit doesn’t show systematic deviations of the data points from theory.  

3. Do the same with other plausible distributions.  

4.  Decide which of the fits looks best to you.  

Don't be discouraged if step 4 isn't always obvious! It just takes a little practice. The following exercises are designed to build some intuition on that. 
