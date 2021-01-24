

## SRE: Logging onto machine for first time

These are important notes to supplement those from [MyPopData](https://my.popdata.bc.ca/html/SRE/mac/connecting.html)

### Assumptions: 
- already installed: 
    - Cisco AnyConnect for VPN (not typicall on Mac nor Windows)
    - Microsoft Remote Desktop (not typicall on Mac)


1. Plug in Yubikey

2. Update passphrase on https://my.popdata.bc.ca/password (may keep the same one) to synchronize the activated project folder

3. AnyConnect VPN [see more details](https://my.popdata.bc.ca/html/SRE/mac/connecting.html)

  - ```access.popdata.bc.ca``` as address
  - Group: ```sreyubi```
  - *DO NOT PRESS ENTER; DO NOT CLICK OK; instead, touch on copper on your Yubikey*

4. RDP
  - PC name must match exactly, e.g. "fast1", not "fast 1"

 

