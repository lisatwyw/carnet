
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

```
%inc 'R:\working\library\macros.sas';    /* Include library */

proc sql;
  create table demog as
    select A.studyid, A.dob, A.sex, B.death_dt as death_date
    from C as A left join raw_data.deaths as B on A.studyid = B.studyid
quit;

proc contents data = C;
  title 'Demographic data';
run;

```


