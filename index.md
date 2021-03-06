---
title       : Error Rate Calculator
subtitle    : 
author      : Rodrigo Peres Ferreira
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Error Rate Input

The Error Rate Calculator aims to generate the values of the most common error measures for evaluating prediction tests that use discrete data.

The Input of this program consists of a matrix containing the measures of True Positives (TP), False Positives (FP), True Negatives (TN) and False Negatives (FN).

- The True Positives (TP) measure indicates how many times the data was correctly identified according to the reality;
- The False Positives (FP) measure indicates how many times the data was incorrectly identified, i.e., the data did not present the attribute that the test has indicated.
- The True Negatives (TN) measure indicates how many times the data was correctly rejected, i.e., the test hasn't identified the attribute in the data, and the data didn't present this attribute in the real world.
- The False Negatives (FN) measure indicates how many times the data was incorrectly rejected, i.e., the data had the attribute the test was trying to identify, but the test failed to recognize it.

--- .class #id 

## Error Rate Output

This program outputs 5 error rate measures:

- Sensitivity: It is the probalitity that the test identified the attribute in the data given that the data really had that attribute. It is calculated by the given formula: Sensitivity = TP/(TP + FN). 
- Specificity: It is the probalitity that the test did not identify the attribute in the data given that the data really didn't present that attribute. It is calculated by the given formula: Specificity = TN/(TN + FP). 
- Positive Predictive Value (PPV): It is the probalitity that the data really presented the attribute given that the test has identified that attribute. It is calculated by the given formula: PPV = TP/(TP+FP).
- Negative Predictive Value (NPV): It is the probability that the data did not presented the attribute given that the attribute wasn't identified by the prediction test. It is calculated by the given formula: NPV = TN/(TN + FN).
- Accuracy: It is the probability that the test identify or reject the data correctly. It is calculated by the given formula: (TP + TN)/ (TP + FP + TN + FN).

---

## An example

If the Error Rate Input contains the following;


```r
TP <- 10
FP <- 2
TN <- 12
FN <- 1
```

Then the output error measures for Sensitivity and Specitivity are going to be the following:


```r
(Sensitivity <- TP/(TP + FN)) 
```

```
## [1] 0.9091
```

```r
(Specificity <- TN/(TN + FP)) 
```

```
## [1] 0.8571
```

---

## An example

And the Positive Predictive Value (PPV), Negative Predictive Value (NPV) and Accuracy are going to be the following:


```r
(PPV <- TP/(TP+FP))
```

```
## [1] 0.8333
```

```r
(NPV <- TN/(TN + FN))
```

```
## [1] 0.9231
```

```r
(Accuracy <- (TP + TN)/ (TP + FP + TN + FN))
```

```
## [1] 0.88
```
