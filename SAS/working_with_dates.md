## Functions
```
datepart()
timepart()
year()
month()
day()
```

## Converting from string to date type

If you have column of dates in "string format" (e.g. 12AUG1921), you'll need to convert to date

```
proc sql;
  select dob format=date9. as dob, Diag_date format=date9. as Diag_date, year(dob)-year(Diag_date) as age_at_dx from incident;
quit;
```

## Precision: minute, hour, day, year

```
proc sql;
  select intck( 'year', dob_year_format, dod_year_format) as age_at_death from incident;
quit;
```

```
proc sql;
  select intck( 'minute', out_min_format, in_min_format) as duration_in_er from EDvisits;
quit;
```
