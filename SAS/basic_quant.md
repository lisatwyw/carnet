## means 

- If ```var``` not specified, then calculate means for all numeric variables

```
proc means data = sasdata.hosp;
  class province;
  var baby_wt; 
run;
```

For larger tables:
```
proc means data = sasdata.hosp;  
  by province; 
  var baby_wt;
run;
```
```
proc means data = sasdata.hosp n nmiss mean min Q1 median Q3 max;
  class province;
  var baby_wt; 
  output out=data.summary_stats mean = mean_weight; /* will save stats to file with additional fields _TYPE_, _FREQ_ */    
run;
```

## summary

```
data temp;
  set sasdata.hosp;
  
  if admcat = 'U' then urgent = 1; else urgent=0;
  if admcat not in {'U'} then delete;
run;

proc sort data = temp;
  by ID;
run;

proc summary data = temp;
  by ID;
  output out = counts sum=;
run;
```


## freq

## univarate

generate histogram
