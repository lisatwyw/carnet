# Notes on R and R Studio


## Common libraries

```
library(randomForest)
library(survival)
library(ranger)  # Survival Random Forest
library(doMC)

library(keras)
library(xgboost)

library(mlbench)

library(party) # conditional incident forest
library(pec)   # calc prediction error curves
library(dplyr) # data manipulation
library(caret) # stratified cross-valiation

#library()
```

## Common snippets

```
df  <- read_sas('database.sas7bdat')
summary( df )
```

```
inds <- which( df$dx_year < 2010)
```

```
time2death = as.numeric( difftime( df$dod, df$dx_date, units="days" ))
time2death[ which(is.na(time2death)) ] <- df$enddate[ which(is.na(time2death))  ]  # missing values now censored by end of study date
```

```
starttime <- proc.time()
# do stuff
run_time <- proc.time() - starttime
```

```
rsf <- ranger( Surv(time2death,status) ~., data=df )
rsf = predict( rsf, tst_df )

# mtry: randomly select 3 features
rsf2 <- rfsrc( Surv(time2death,status) ~., data=df, ntree=100, nodesize=5, mtry=3, nsplit=3, importance=TRUE )
fimp = vimp( rsf2, importance = "permute")
```


## Multi-Core processing

Details at https://r-forge.r-project.org/R/?group_id=947

```
install.packages("doMC", repos="http://R-Forge.R-project.org")
```


