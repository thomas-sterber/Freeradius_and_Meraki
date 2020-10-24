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


## tested setups


| authentication                    | MR55 | MS350| MX65|
|                                   |(27.5)|(14.4)|(15.38)|
| --------------------------------  | -----| --- | --- |
| 802.1X                            | yes  | yes | yes |
| 802.1X + VLAN                     | yes  | yes | |
| 802.1X + GroupPolicy              | yes  | | |
| 802.1X + GroupPolicyACL           | | tbd | |
| 802.1X + VLAN + GroupPolicyACL    | | tbd | |
||| 
| MAB                               | yes | yes  | |
| MAB + VLAN                        | yes | yes  | |
| MAB + GroupPolicy                 | yes | | |
| MAB + GroupPolicyACL              | | tbd | |
| MAB + VLAN + GroupPolicyACL       | | tbd | |
|||
| iPSK                              | yes | | |
| iPSK + VLAN                       | yes | | |
| iPSK + GroupPolicy                | yes | | |


Adaptive Policy

| authentication                    | MR   | MS 390  |
|                                   |(27.5)|(14.4)|
| --------------------------------  | -----| --- |
| 802.1X and SGT assignment         | tbd | tbd |
| MAB  and SGT assignment           | tbd | tbd |








