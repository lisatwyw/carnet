
# RSF

```
from sksurv.ensemble import *

model = RandomSurvivalForest( ... )

predicted_survs = model.predict_survival_function( X )

YP = np.asarray( [[ fn(t) for t in times] for fn in survs ])

```
