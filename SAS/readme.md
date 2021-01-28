
# Quick dive into SAS/IML Studio 14.3

Coming


# Quick dive into SAS 7.0

## Control

- ```Run``` (stickman figure) icon to execute code
- ```Control``` + ```E``` to clear log


## Tips

- Tile scripts vertically/ horizontally with:
  ```Window > Tile ...``` 

## Same as Python

- ```/*  this is a comment */```
- Highlight and run sections: select code snippets and then click ```Run``` will execute only selected code snippets  


## Examples

### Joining two tables using SQL syntax; commenting, show summary of table
```
/* Below include library at noted location */
%inc 'R:\working\library\macros.sas';    



/* Below generates SQL query to join 2 tables using studyid as keys */
proc sql;
  create table demog as
    select A.studyid, A.dob, A.sex, B.death_dt as death_date
    from C as A left join raw_data.deaths as B on A.studyid = B.studyid
quit;


/* Below will generate summary table for C */ 
proc contents data = C;
  title 'Demographic data';
run;

```


### Sort records by StudyID, then by descending death_dt
```
proc sort data=demo; by StudyID descending death_dt; run;
```

### Output the first occurrence for each studyid (second occurrence will be dropped)
```
data demo;
  set demo;
  by studyid;
  if first.studyid then output;
run;
```
