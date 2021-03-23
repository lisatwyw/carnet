
```
HISTTIMEFORMAT="%d/%m/%y %T "
```

# Build of VM on cedar on 2021-01-11
```
  cd ~/proj
  module getdefault
  module load gcc/5.4.0 opencv/3.3.0 python/3.6
  python3.6 -m venv py3.6-tf
  source py3.6-tf/bin/activate
  pip install tensorflow-gpu==2.2.0 keras==2.4.2 # took out version number of keras
  pip install nibabel matplotlib scikit-learn pillow pandas pydicom tqdm seaborn  scipy ipython  
  pip install --upgrade --force-reinstall torch==1.5.0

```

## ComputeCanada (CC) & CalculQuebec (CQ)

### File transfers via Globus

#### Logging in
1) Sign-up https://globus.computecanada.ca/ (you can use gmail)
2) On far left menu (dark blue), choose ```File Manager```
3) Under ```Collection``` on left side, search for helios (the full identifier is ```computecanada#helios-dtn```)
4) On the right side, search for destination in a similar fashion or type in identifier as ```computecanada#cedar-dtn```, ```computecanada#beluga-dtn```, ```computecanada#graham-dtm``` for cedar, beluga, graham, respectively
5) Login on the destination

#### Transfers
6) On left side, choose the folder in helios where you want to copy entirely
7) On right side, choose folder of destination node where you want the folder to be copied to 
8) Click blue button marked with ```Start``` and arrow on the left side
Optional) To copy in opposite direction, use the ```Start``` arrow button on the right side

Notes:
- Beluga/ Helios are both maintained by East Canada/ French-speaking staff (CQ)
- Cedar/ Graham are by West (CC), e.g. UBC/SFU/Alberta
