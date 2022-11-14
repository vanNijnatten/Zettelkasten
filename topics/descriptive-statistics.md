---
tags: 🏛 🔖 
aliases: 
  - descriptive statistics
cssclass: idea
publish: true
---
# Descriptive Statistics

## Arithmetic Mean
$$\overline{Y}=\frac{\sum Y}{n}$$
**Weighted Average**
$$\overline{Y}_{w}=\frac{\sum\limits^{n} w_i Y_i}{\sum\limits^{n} w_i}$$
This is the average over two samples, thus as if the two samples are one. However you only know the average of the property (you want to calculate the average over) for each sample. In the formula above, the $\overline{Y}_w$ is the weighted average, $n$ is the number of samples, $w_i$ is the weight of the current sample (or the amount of measurements in the current sample), and $Y_i$ is the arithmetic mean of the current sample.

*Example*: The arithmetic mean of the weight of all children (n=25) in one classroom is 44.7kg, and the arithmetic mean of the weight of all children (n=27) in another classroom is 41.5kg. The weighted average is 
$$\frac{(44.7\times25)+(41.5\times27)}{25+27}=43.04$$

## Geometric Mean
$$GM_Y=\sqrt[n]{\prod_{i=1}^n Y_i}$$
$$GM_Y=antilog\frac{1}{n}\sum \log Y$$

## Harmonic Mean
$$\frac{1}{H_Y}=\frac{1}{n}\sum\frac{1}{Y}$$

## Median
Middle value in an ordered list of values, or the arithmetic mean of the two middle values.

## Quantiles
Median is the 50% quantile. Other quantiles are 25% and 75% (half of the middle). These examples are also called quartiles.

## Mode
Value most frequent present in the list of values. Distributions with two 'peaks' are called bimodal. Distributions with more 'peaks' are called multimodal.

## Range
$$R_Y=\max{Y}-\min{Y}$$

## Standard Deviation
Individual error:
$$y=Y-\overline{Y}$$
Variance:
$$Variance=\frac{\sum y^2}{n}$$
Standard deviation:
$$SD=\sqrt{Variance}$$
AKA:
$$SD=\sqrt{\frac{\sum\left(Y-\overline{Y}\right)^2}{n}}$$
## Coefficient of Variation
SD expressed as a percentage of the mean. This is a biased estimator of the population V. Also called 'relative standard deviation'.
$$V=\frac{SD\times100}{\overline{Y}}$$
The following is corrected for bias:
$$V^\ast=\left(1+\frac{1}{4n}\right)V$$
