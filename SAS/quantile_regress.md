#  Quantile regression (QR)

[PopDataBC Webinar 2021-Jan-27](https://www.youtube.com/watch?v=b6HMdUe9gy4&feature=emb_logo)

## Introduction

### SAS code
```
proc glm data = sample_skewed_dataset;
  model y = x;
run;
```

### Example

```
y = 6.7220477 + 0.083893 x
```

- Results: intercept and slope (t value, Pr > |t|, R-square, coeff var, )
- SAS's SGplot to visualize result
- As long as residuals sum to zero, independent of each other, then the model is considered unbiased


## Inference
- confidence interval tells us how confident we can be with the prediction
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
- no assumptions about distribution
- less affected by outliers
- solved iteratively, no closed form solution, also no closed form solution for standard errors
- bootstrap to obtain standard errors/ c.i. 

  ```
  ods graphics on; /*output delivery service*/

  proc quantreg data = sample_skewed_dataset; 
    ci =resampling; 
    model y = x / quantiles = 0.5 plot=fitplot (showlimits);
  run;

  ods graphics off;
  ```

  ```
  Median y = 5.9267 + 0.0942 x
  ```


## Terms

- quantile: 0.25, 0.75
- percentile: 0-100


## Quantile Regression

- Often we'd like 90th percentile, e.g. to assess system for most patients

  ```
  proc quantreg data = sample_skewed_dataset; 
    ci =resampling; 
    model y = x / quantiles = 0.95 plot=fitplot (showlimits);
  run;
  ```

#### Example with interactions (\*) birth weight of babies

```
proc quantreg data = sashelp.bweight ci=sparsity/ iid algorithm=interior (tolerance=1.e-4); 

  class visit momedlevel; /* categories */
  model weight = black married boy visit momedlevel cigsperday momsmoke momage 
  momage*momage momwtgain momwtgain*momwtgain / quantile = 0.05 to 0.95 by 0.05 plot=quantplot;
  
run;
```   

- hold everything constant, the plot allows us to see...
- x axis is the range of baby weight

Observations:

1. sex: boys tend to weigh more
  - difference in baby sex is more pronounced for heavier baby boys (150g for boys vs 60 girls) 

2. martial status: not married on left-hand side 

3. race: black mother; constant vs curved slopes 
  - ```-200 grams``` in black mothers 
  

## Caveats

- Continuous values work; does not work for binary outcomes (since 90th percentile of binary variable makes little sense)
- Counts should work
  
### Remedies when central tendency assumption is invalid

- transformation, e.g. log 
- weighted regression
  




