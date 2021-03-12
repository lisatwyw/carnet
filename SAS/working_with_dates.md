

## Converting from string to date type

If you have column of dates in "string format" (e.g. 12AUG1921), you'll need to convert to date

```
proc sql;
  select datepart( dob format=date9.) - datepart( Diag_date format=date9.) from incident;
quit;
```

## Precision: minute, hour, day, year

```
proc sql;
  select intck( 'year', dob format=year9., dod format=year9.) as age_at_death from incident;
quit;
```


```
proc sql;
  select intck( 'minute', out format=minute9., in format=minute9.) as duration_in_er from EDvisits;
quit;
```
