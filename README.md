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


| authentication                    | MR55 (27.5)| MS350 (14.4)| MS390 (14.5)|MX65 (15.38)|
| --------------------------------  | -----| --- |--- | --- |
| 802.1X                            | yes  | yes |yes| yes |
| 802.1X + VLAN                     | yes  | yes |yes| |
| 802.1X + GroupPolicy              | yes  | || |
| 802.1X + GroupPolicyACL           | | yes |na| |
| 802.1X + VLAN + GroupPolicyACL    | | yes |na| |
||| 
| MAB                               | yes | yes  |yes| |
| MAB + VLAN                        | yes | yes  |yes| |
| MAB + GroupPolicy                 | yes | || |
| MAB + GroupPolicyACL              | | yes |na| |
| MAB + VLAN + GroupPolicyACL       | | yes |na| |
|||
| iPSK                              | yes | || |
| iPSK + VLAN                       | yes | || |
| iPSK + GroupPolicy                | yes | || |
| iPSK + SGT                        | yes | || |


Adaptive Policy  MS390

| authentication                    | MR (27.5)| MS 390 (14.5)|
| --------------------------------  | -----| --- |
| 802.1X and SGT assignment         | yes | yes |
| MAB  and SGT assignment           | yes | yes |








