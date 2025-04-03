## Pip List

### Worked in python 3.12 
```
import pkg_resources

# Get the working set (all installed packages)
working_set = pkg_resources.working_set

# Iterate through the distributions (packages)
for distribution in working_set:
  print(f"{distribution.project_name}=={distribution.versi
```

### Did not work in python 3.12
```
from pip.operations import freeze    
modules = list(
    map(lambda x: x.split('=='), freeze.freeze(local_only=True))
)  

import pip
modules = []
for i in pip.utils.get_installed_distributions():
    modules.append((i.key, i.version))
```

## Not avail in py 3.12
```
from pip._internal.utils.misc import get_installed_distributions  
p = get_installed_distributions()
pprint.pprint(p)
utils.st.write( p ) 

#from pkgutil import iter_modules
#utils.st.write([p.name for p in iter_modules()])
```

## Pip freeze
```
try: 
  from pip._internal.operations import freeze      
  utils.st.write( '1' ) 
except ImportError: # pip < 10.0
  from pip.operations import freeze
  utils.st.write( '2' ) 

pkgs = freeze.freeze()
print( pkgs )
``` 


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




