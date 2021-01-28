# Examples (from a Python coder)

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
proc sort data=C; by StudyID descending death_dt; run;
```

### Output the first occurrence for each studyid 

- second occurrence will be dropped
- result will be saved as sas7dbat under FOLDER with prefix FILENAME

```
data FOLDER.FILENAME;
  set C;
  by studyid;
  if first.studyid then output;
run;
```
