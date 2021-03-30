

```
%macro comorbs();

%mend comorbs;
```

```
%macro search();

%mend search;
```

```
%macro hsp_comorbid( icd10_code, suffix);

  %let elective_cateract = prxparse('/H26|H26/');
  if prxmatch(&elective_cateract, &icd10_code) > 0 then elective_cateract_&suffix=1; 

%mend hsp_comorbid;
```
- creates a variable ```elective_careract_```suffix```


```
do i=1 to 25;
  dx10=icd10(i)
  dt=dtype(i)

  hsp_comorbid(dx10, suffix)
  
end;
```
