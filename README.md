# Using Freeradius for Meraki on Raspberry

This guide is to easily setup a Freeradius which can be used as a AAA for a Meraki authentication tests in your LAB or POC.

## installation instructions

### prepare Raspberry
- install fresh Raspian OS
- enable ssh
- enable ssh for root
- install Freeradius v3.0
- create on your laptop a local folder and download the repository 


### Start the Freeradius Management GUI for Meraki
The script configure_freeradius_for_meraki.py will configure the Freeradius to work with Meraki.
All tested setups will be available.
You need to know the management IPs of the Meraki devices. ??   all
?? shared secret 'meraki123'

./meraki-freeradius-gui.py

### files 
meraki-freeradius-gui.py
users
clients.conf
...


## supported setups


| authentication                    | MR   | MS  | MX  | 
| --------------------------------  | -----| --- | --- |
| 802.1X                            | yes  | yes | yes |
| 802.1X and vlan assignment        | yes  | yes | |
| 802.1X and GroupPolicy assignment | yes  | yes | |
||| 
| MAB                               | yes | yes  | |
| MAB and vlan assignment           | yes | yes  | |
| MAB and GroupPolicy assignment    | yes | yes  | |
|||
| 802.1X and SGT assignment         | tbd | | |
| MAB  and SGT assignment           | tbd | | |
|||

tested:
- MR55
- MS220-8P, MS350
- MX65
- AdaptivePolicy SGT assignment:  MR45, MS390






