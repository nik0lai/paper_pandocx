---
title: 'Title'

institute:
  - uva: Department of Psychology, University of Amsterdam
  - abc: Amsterdam Brain & Cognition, University of Amsterdam
  - vu: Department of Applied and Experimental Psychology, Free University Amsterdam
  - ibba: Institute for Brain and Behavior Amsterdam, Free University Amsterdam
author:
  - Nicolás Sánchez-Fuenzalida:
      institute: [uva, abc, vu, ibba]
  - Johannes J. Fahrenfort:
      institute: [uva, abc, vu, ibba]
reference-section-title: References
# using this field will render the abstract before the author affiliations. alternatively you can write the abstract directly as markdown text
abstract: "Some abstract"

# this allows me to add an S to the figures/text/sections of the supplementary
# adding {-} to the headers of the main document will remove the extra numnbering that is replaced with and S in the supplementary
chapters: True
chaptersDepth: 1
chapDelim: ""
---

\newpage

# Introduction {-}

Lorem ipsum dolor sit amet, consectetur adipiscing elit. In tempus ornare lacus, a mollis nunc gravida vel. Sed eleifend nisl magna, eu molestie mi ornare quis. Mauris feugiat dolor sit amet euismod molestie. Nullam commodo purus a sodales bibendum. Maecenas sem arcu, porttitor nec augue eget, egestas consequat odio. Maecenas tincidunt augue vitae semper elementum. Sed ac urna quis tellus aliquet consectetur. Curabitur vulputate id ligula eget gravida. Vivamus ut odio eu enim ornare commodo. Duis euismod mi ut sapien vulputate fringilla. Duis placerat turpis sed sodales suscipit [@franckenAcademicSurveyTheoretical2022]. 

Sed sodales fermentum ligula, ac pharetra nibh tristique vitae. Donec faucibus fermentum sem a tempor. Donec tincidunt id dui sit amet viverra. Pellentesque vitae arcu vestibulum, finibus est in, pulvinar metus. Quisque suscipit in libero vel elementum. In libero quam, tempus at dui et, volutpat vulputate orci. Nam at luctus eros. Maecenas elementum ut ex eget rhoncus. Donec suscipit orci in volutpat tincidunt. Etiam vulputate eget magna eu maximus [@fahrenfortCriterionPlacementThreatens2024; @steinCanWorkingMemory2016; @steinHumanVisualSystem2021]. 

![**Experiment 1. Trial layout, bias manipulation summary and main results**.](figures/fig1.pdf){#fig:exp1TrialManipulationResults width=95%}

\newpage

# References {-}

::: {#refs}
:::

\newpage

# Supporting Information {label="S"}

## {label=''}

### Text [-@sec:suppText]: Supplementary text {#sec:suppText}

 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed eget purus odio. Suspendisse placerat dapibus felis nec finibus. Aliquam eu lacus at odio tempus blandit quis nec orci. Ut diam tortor, pharetra in tellus id, tempus blandit urna. Quisque egestas non dui eget mattis. Donec consectetur eros ac nulla interdum consectetur ac quis elit. Sed in ipsum arcu. Cras pulvinar mollis dolor sed lobortis. Sed placerat, orci ut laoreet viverra, quam massa tempus turpis, nec luctus magna nisl vel libero. Duis gravida tincidunt vehicula. Praesent porttitor nulla libero, non sollicitudin eros faucibus in. Aenean mollis at ex eget eleifend. Nulla justo tellus, finibus eget efficitur sed, facilisis id lacus. Curabitur accumsan diam vel mauris lacinia, sed venenatis turpis mattis. Donec posuere, lorem sed molestie ornare, lorem ligula mattis sem, a gravida dolor nibh ut urna. Sed pharetra aliquet mi, sed semper libero placerat a. 

\newpage

### Text [-@sec:suppTable]: Supplementary multi-line table like {#sec:suppTable}

 Sed sodales fermentum ligula, ac pharetra nibh tristique vitae. Donec faucibus fermentum sem a tempor. Donec tincidunt id dui sit amet viverra. Pellentesque vitae arcu vestibulum, finibus est in, pulvinar metus. Quisque suscipit in libero vel elementum. In libero quam, tempus at dui et, volutpat vulputate orci. Nam at luctus eros. Maecenas elementum ut ex eget rhoncus. Donec suscipit orci in volutpat tincidunt. Etiam vulputate eget magna eu maximus.   
  
-------------

Sed sodales fermentum ligula,  
ac pharetra nibh tristique vitae.  
Donec faucibus fermentum sem a tempor.  
Donec tincidunt id dui sit amet viverra.

-------------

Sed sodales fermentum ligula,  
ac pharetra nibh tristique vitae.  
Donec faucibus fermentum sem a tempor.  
Donec tincidunt id dui sit amet viverra.

\newpage

### Text [-@sec:suppFormula]: Some mathy formulae {#sec:suppFormula}

Four Hurdle-gaussian models of increasing complexity were fit to the reproduction responses data using the *brms* R package (version 2.20.4) for Bayesian Multilevel Models[@burknerBrmsPackageBayesian2017]. For each model we ran four Markov chain Monte Carlo (MCMC) with 10,000 iterations each, 5,000 warm up iterations and a thinning factor of 1. All R-hat values were lower or equal to 1.02. The Hurdle-Gaussian model consists of a binary part (Bernoulli distribution) that indicates the probability of a given contrast value to pass the hurdle and a (Gaussian distribution) part that describes the values that went over the hurdle. For an outcome variable $y$ (in our case a reproduction response), the model assumes that $y$ will be zero or normally distributed depending on the probability of $hu$:

$$
y \sim 
\begin{cases} 
0 & \text{with probability } \text{hu}, \\
\text{Normal}(\mu, \sigma) & \text{with probability} 1 - \text{hu}.
\end{cases}
$$

Where $\mu$ is the mean of the normal distribution (mean *non-zero* reproduced contrast) and $\sigma$ is the standard deviation of the normal distribution. $\text{hu}$ is the hurdle component that indicates the probability of $y$ being zero, modelled using Bernoulli distribution with logit link function. The likelihood function is:

$$
\text{log } P(y \mid \mu, \sigma, \text{hu}) = 
\begin{cases} 
\text{logit}(\text{hu}) & \text{if } y = 0, \\
\text{log}(1 - \text{hu}) + \text{Normal}(y \mid \mu, \sigma) & \text{if } y > 0.
\end{cases}
$$

In the full model, response and hurdle depended on the interaction between the contrast of the target patch ($stim$) and condition (control or biased) ($cond$). We also allowed a random slope per participant and condition.

$$
\text{Response: } y \sim \text{stim} \times \text{cond} + (\text{cond} \mid \text{participant})
$$

$$
\text{Hurdle: } \text{hu} \sim \text{stim} \times \text{cond} + (\text{cond} \mid \text{participant})
$$

\newpage
