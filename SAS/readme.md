
# SAS

SAS = Statistical Analysis Software

# Quick dive into SAS 7.0

## Control

- ```Run``` (stickman figure) icon to execute code
- ```Control``` + ```E``` to clear log
- Explorer: to view the list of variables in memory 

## Tips

- Tile scripts vertically/ horizontally with:
  ```Window > Tile ...``` 

## Same as Python

- ```/*  this is a comment */```
- Highlight and run sections: select code snippets and then click ```Run``` will execute only selected code snippets  
- Sorting: capital letters first, then lower case characters

## Database examples

- [See few examples from a Python programmer new to SAS](examples.md)
- [SAS tutorial: 3 steps to build macro program](https://www.youtube.com/watch?v=Fe_Efkl3enM)


## Data analyses examples

- [Quantile](quantile_regress.md) 

- Calculate means for all numeric variables
  ```
  proc means data = sample_data;
    class province;
    var baby_wt; 
  run;
  ```
  
  For larger tables:
  ```
  proc means data = sample_data;  
    by province; 
    var baby_wt;
  run;
  ```




# Quick dive into SAS Enterprise Guide

- [Extract timeseries using wizard](https://www.youtube.com/watch?v=K-lR8lJpg1k)



# Quick dive into SAS/IML Studio 14.3

...Coming



