# First-time examples (from a Python developer's perspective)

### Simple join of two tables
```
Data JoinedDS;
  set folder.database1 folder.database2; 
run;

/* new table exists in memory (working session) only, not saved to file */
```

```
/* below will save to FOLDER  */

Data FOLDER.JoinedDS;
  set folder.database1 folder.database2; 
run;
```


### Joining two tables using SQL syntax; commenting, show summary of table

- Usually SQL preferred over data

```
/* Below generates SQL query to join 2 tables using studyid as keys */
proc sql;
  create table demog as
    select A.studyid, A.dob, A.sex, B.death_dt as death_date
    from 
    raw_data.births as A
        left join 
    raw_data.deaths as B     
        on A.studyid = B.studyid
    order by A.studyid, B.dob;
quit;


/* Below will generate summary table for C */ 
proc contents data = C;
  title 'Demographic data';
run;

```


### Macros
```
/* Below include library at noted location */
%inc 'R:\working\library\macros.sas';    

%macro MACRO_NAME;
/* */
%mend MACRO_NAME;

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

### Histograms

```
proc univariate data = E;
  var max;
  histogram;
  run;
```
