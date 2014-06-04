---
title       : Homework 2 for Stat Inference
subtitle    : Extra problems for Stat Inference
author      : Brian Caffo
job         : Johns Hopkins Bloomberg School of Public Health
framework   : io2012
highlighter : highlight.js  
hitheme     : tomorrow       
#url:
#    lib: ../../librariesNew #Remove new if using old slidify
#    assets: ../../assets
widgets     : [mathjax, quiz, bootstrap]
mode        : selfcontained # {standalone, draft}
---



## About these slides
- These are some practice problems for Statistical Inference Quiz 1
- They were created using slidify interactive which you will learn in 
Creating Data Products
- Please help improve this with pull requests here
(https://github.com/bcaffo/courses)
runif(1)

--- &radio
The probability that a manuscript gets accepted to a journal is 12% (say). However,
given that a revision is asked for, the probability that it gets accepted
is 90%. Is it possible that the probability that a manuscript has a revision
asked for is 20%? 

1. Yeah, that's totally possible.
2. _No, it's not possible._
3. It's not possible to answer this question.

*** .hint
$A = accepted$, $B = revision$. $P(A) = .12$, $P(A | B) = .90$. $P(B) = .20$

*** .explanation
$P(A \cap B) = P(A | B) * P(B) = .9 \times .2 = .18$ this is larger than
$P(A) = .12$, which is not possible since $A \cap B \subset A$.


--- &radio
Suppose that the number of web hits to a particular site are approximately normally
distributed with a mean of 100 hits per day and a standard deviation of 10 hits per day. What's the probability that a given day has fewer than 93 hits per day
expressed as a percentage to the nearest percentage point?

*** .hint
Let $X$ be the number of hits per day. We want $P(X \leq 93)$ given that
$X$ is $N(100, 10^2)$.

*** .explanation

```r
round(pnorm(93, mean = 100, sd = 10) * 100)
```

```
[1] 24
```



--- &radio
Suppose 5% of housing projects have issues with asbestos. The sensitivity of a test
for asbestos is 93% and the specificity is 88%. What is the probability that a 
housing project has no asbestos given a negative test expressed as a percentage
to the nearest percentage point?

1. 0%
2. 5%
3. 10%
4. 20%
5. 50%
6. _100%_

*** .hint
$A = asbestos$, $T_+ = tests positive$, $T_- = tests negative$. 
$P(T_+ | A) = .93$, $P(T_- | A^c) = .88$, $P(A) = .05$.

*** .explanation
We want
$$
P(A^c | T_-) = \frac{P(T_- | A^c) P(A^c)}{P(T_- | A^c) P(A^c) + P(T_- | A) P(A)}
$$

```r
(.88 * .95) / (.88 * .95 + .07 * .05)
```

```
[1] 0.9958
```




---  &radio
Suppose that the number of web hits to a particular site are approximately normally
distributed with a mean of 100 hits per day and a standard deviation of 10 hits per day. What number of web hits per day represents the number so that only
5% of days have more hits? Express your answer to 3 decimal places.

*** .hint
Let $X$ be the number of hits per day. We want $P(X \leq 93)$ given that
$X$ is $N(100, 10^2)$.

*** .explanation

```r
round(qnorm(.95, mean = 100, sd = 10), 3)
```

```
[1] 116.4
```

```r
round(qnorm(.05, mean = 100, sd = 10, lower.tail = FALSE), 3)
```

```
[1] 116.4
```



---  &radio
Suppose that the number of web hits to a particular site are approximately normally
distributed with a mean of 100 hits per day and a standard deviation of 10 hits per day. Imagine taking a random sample of 50 days. What number of web hits would
be the point so that only 5% of averages of 50 days of web traffic have more hits? 
Express your answer to 3 decimal places. 

*** .hint
Let $\bar X$ be the average number of hits per day for 50 randomly sampled days.
$X$ is $N(100, 10^2 / 50)$.

*** .explanation

```r
round(qnorm(.95, mean = 100, sd = 10 / sqrt(50) ), 3)
```

```
[1] 102.3
```

```r
round(qnorm(.05, mean = 100, sd = 10 / sqrt(50), lower.tail = FALSE), 3)
```

```
[1] 102.3
```


