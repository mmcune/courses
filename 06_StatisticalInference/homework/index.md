---
title       : Homework 1 for Stat Inference
subtitle    : Extra problems for Stat Inference
author      : Brian Caffo
job         : Johns Hopkins Bloomberg School of Public Health
logo        : bloomberg_shield.png
framework   : io2012
highlighter : highlight.js  
hitheme     : tomorrow       
url:
    lib: ../../librariesNew #Remove new if using old slidify
    assets: ../../assets
widgets     : [mathjax, quiz, bootstrap]
mode        : selfcontained # {standalone, draft}
ext_widgets : {rCharts: ["libraries/highcharts","libraries/nvd3", "libraries/morris", "libraries/leaflet", "libraries/rickshaw"]}
--- &radio



Consider influenza epidemics for two parent heterosexual families. Suppose that the probability is 15% that at least one of the parents has contracted the disease. The probability that the father has contracted influenza is 6% while that the mother contracted the disease is 5%. What is the probability that both contracted influenza?

1. 15%
2. _1%_
3. 6%
4. 5%

*** .hint
$A = Father$, $P(A) = .06$, $B = Mother$, $P(B) = .05$ 
$P(A\cup B) = .15$, 



*** .explanation
$P(A\cup B) = P(A) + P(B) - 2 P(AB)$ thus
$$.15 = .06 + .05 - 2 P(AB)$$


