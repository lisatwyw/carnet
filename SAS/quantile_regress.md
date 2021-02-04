#  Quantile regression

[PopDataBC Webinar 2021-Jan-27](https://www.youtube.com/watch?v=b6HMdUe9gy4&feature=emb_logo)

## Introduction

### SAS code
```
proc glm data = sample;
  model y = x;
run;
```

### Example

```
y = 6.7220477 + 0.083893 x
```

- Intercept and slow
- SG plot to visualize result
- As long as residuals sum to zero, independent of each other, then the model is considered unbiased


## Inference
- confidence interval
- standard error (drawn from data) 
- grey area too narrow on right: fails to represent the uncertainty on the right
- grey area too wide on left:
    - residuals need to be normally distributed 
    - residuals need to have constant variation 


### Ordinary least-squares regression (OLS)
- mean is not good measure of central tendency for **skewed distributions**
- even few outliers affect regression model

### Median regression 
- rather than to predict average, **predict median**


