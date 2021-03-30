

```
%macro comorbs();

%mend comorbs;
```

```
%macro search();

%mend search;
```


```
%macro comorbid_index(varlist, suffix);

  %let nvar=%sysfunc( countw( &varlist.));

  %do i=1 %to &nar;
    
  %end;
  
%mend comorbid_index;
```



Macro that would create a variable ```elective_careract_```suffix```:
```
%macro hsp_comorbid( icd10_code, suffix);

  %let elective_cateract = prxparse('/H26|H26/');  /* ICD10 */
  if prxmatch(&elective_cateract, &icd10_code) > 0 then elective_cateract_&suffix=1; 

%mend hsp_comorbid;
```


Loop over 25 diagnositic codes to check whether those defined in hsp_omorbid would be found, i.e.  elective_cateract_test:
```
do i=1 to 25;
  dx10=icd10(i)
  dt=dtype(i)
  %hsp_comorbid(dx10, test)  
end;
```

