

## List comprehension with exception handling

```
    import pandas as pd; missing = []    
    
    def catch(func, handle=lambda e : e, *args, **kwargs):
        try:            
            return func(*args, **kwargs)
        except Exception as e:
            missing.append( e )
            return handle(e)        
            
    combined_csv = pd.concat( [catch(lambda : pd.read_csv(f) ) for f in list_filenames]  )      
```    
