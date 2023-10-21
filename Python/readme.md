
## ```Polars```

starts with b and end with any digit
```
(
df.select([
    pl.concat_str(
        pl.col("^b_\d$").fill_null("").alias("new")
        )
    ])
)
```


## List comprehension with exception handling

```
    import pandas as pd; missing = []    
    
    def catch(func, handle=lambda x: x, *args, **kwargs):
        try:            
            return func(*args, **kwargs)
        except Exception as er:
            missing.append( x )
            return None 
            
    all_df = pd.concat( [catch(lambda : pd.read_csv(f) ) for f in list_filenames]  )      
```    
