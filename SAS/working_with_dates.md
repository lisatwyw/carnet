

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
  select intck( 'hour', dob format=date9., dod format=date9.) as age_at_death from incident;
quit;
```
