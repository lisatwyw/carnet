# Getting started notes

- [Secure Research Environment](SRE/readme.md)
- [SAS](SRE/readme.md) 
- [R](R/readme.md) 
- [Notes on Compute Canada](CC/readme.md)





# Common snippets

```
salloc --time=3:0:0 --ntasks=2 --account=def-your_username --mem-per-cpu=24G --gres=gpu:t4:1 --nodes=2



salloc --job-name=live --time=12:0:0 --ntasks=1 --account=def-your_username --gres=gpu:k80:1 --nodes=1 --mem-per-cpu=48G
```
