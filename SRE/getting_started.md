# SRE

## SRE setup

Requests:

| Date | Task | status |
|---|---|---| 
| 2021-Jan-24 | 1. Jupyter Notebook or Lab| pending |
| 2021-Feb-10 | 2. Python packages below | pending |
| 2021-Feb-12 | 3. Tensorflow does not work in Python 3.9 | still true |

### Links
```
access.popdata.bc.ca
POPDATA\ltang-18-095
```
```
fast8.popdata.bc.ca
sre60.popdata.bc.ca   # read below!!!
```
 
 

## Logging onto machine for first time

These are important notes to supplement those from [MyPopData](https://my.popdata.bc.ca/html/SRE/mac/connecting.html). Assumptions: 
- You've already installed: 
    - Cisco AnyConnect for VPN (not typicall on Mac nor Windows)
    - Microsoft Remote Desktop (not typicall on Mac)

1. Plug in Yubikey

2. Update passphrase on https://my.popdata.bc.ca/password (may keep the same one) to synchronize the activated project folder

3. AnyConnect VPN [see more details](https://my.popdata.bc.ca/html/SRE/mac/connecting.html)

      0. ```access.popdata.bc.ca``` as address, click ```Connect```
      1. Group: ```sreyubi```
      2. Enter ```user_name```
      3. *DO NOT PRESS ENTER; DO NOT CLICK OK; instead, touch on copper on your Yubikey*

4. RDP
  - PC name must match exactly, e.g. "fast1", not "fast 1"
  - username on RPD must contain domain name, i.e. ```POPDATA\user_name```

## Transfers in/out

### Setup on local machine:

On Mac: 
1. File Explorer: Go > ```Connect to Server```
2. Enter: 
    ```cifs://PROJECT_SPECIFIC_USERNAME@fraser.popdata.bc.ca/PROJECT_SPECIFIC_USERNAME```     
3. Click ```Connect```
4. Use PROJECT_SPECIFIC_USERNAME when prompted for usename
5. Drag files into ```IMPORT_TO_SRE```

On Windows 10 Home:

1. Right-click on ```This PC```, then ```Add Network Drive```
2. ```\\fraser.popdata.bc.ca\ltang-18-095```
3. Username: PROJECT_SPECIFIC_USERNAME


### On RDP machine:

6. Click ```IMPORT-IT``` (under U:/TRANSFER)
7. Double check that the transfer is allowed and click ```Confirm``` after


## Computing environment
 
### Software

```
ACG John Hopkins version 11.0.1 - more on ACG System Software Licensing Agreement for academic purposes
ArcGIS Desktop 10.6.1
Epi Info 7.2.3.1
GeoDa 1.12.1.161
Gephi 0.9.2.1
graphViz 2.38.0
JoinPoint 4.7.0.0
MPlus 8.3
MS Office 2019
MS Project 2019
MS Visio 2019
Python 2.7.14
Python 3.5.3
R 3.6.1
Rstudio 1.2.1335
Rtools 35
SAS 9.4 TS Level 1M5
SAS EG 7.15 HF8
SaTScan 9.6
SPSS 26 (IBM)
Stat Transfer 13.2
Stata 16
WinBUGS 1.4.3
```

### Utilities
```
7zip 19.00
Acrobat Reader
Active Pearl 5.28.1
Cygwin 5.26.3
git 2.22
MikTex 2.9
Notepad ++ 7.7.1
Putty 0.71
Sublime Text 3207
TextPad 8.2.0
Vim 8.1
WEKA 3.8.3
Wing IDE Personal 7.0
```



### Rules

March-1-2021
```
"Each login is only allowed on one SRE machine at a time."

So for any project account you can only be logged in once. (inclusive regular and fast machines)  
You can contact us for permission to be on more than one machine as a special exception.
Even then, we will not allow more than one login to fast machines, but additional logins on regular machines can be granted.

-- PopData SRE Support Team
```



