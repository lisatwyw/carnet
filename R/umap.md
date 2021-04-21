
# Examples


## Read data and split into train, test subsets

```
library(haven)
df <- read_sas('data.sas7bdat')

omit='SEQNO|Diag_Date' # omit these fields
finds = setdiff( seq( 0, ncol( df)), grep( omit, colnames(df) ))

tst_inds = seq( 0, nrow( df), 100 ) 
trn_inds = setdiff( 0, nrow(df), tst_inds ) 

trn_data<- df[ trn_inds, finds ]
tst_data<- df[ tst_inds, finds ]

```

## umap transformation

```
library(uwot)

tform = umap( trn_data )
emb = umap_transform( tst_data, tform )

t<- read.csv( ) # another variable to color by

# convert to df and add column t
df=as.data.frame( emb )
df$time2death <- t

# plot
ggplot(data=df) + geom_point( mapping = aes( x=x, y=y, color=time2death )

```

See more examples here: https://github.com/jlmelville/uwot
