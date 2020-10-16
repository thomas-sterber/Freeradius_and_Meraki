# Using Freeradius for Meraki on Debian based systems , Raspian

This guide is to easily setup a Freeradius in your lab which can be used as a AAA for a Meraki environment.

## Tested setups
MR
-authentification | tested
- 802.1X | yes 
- 802.1X and vlan assignment | yes
- 802.1X and GroupPolicy assignment | yes
MAB, MAB and vlan assignment, MAB and GroupPolicy assignment

MS
802.1X, 802.1X and vlan assignment, 802.1X and AccessGroupPolicy assignment

MX
802.1X 


## preparation of Raspian
- install fresh Raspian OS
- enable ssh
- enable ssh for root
- install Freeradius v3.0


## installalation
The script configure_freeradius_for_meraki.py will configure the Freeradius to work with Meraki.
All tested setups will be available.
You need to know the management IPs of the Meraki devices. ??   all
?? shared secret 'meraki123'


./configure_freeradius_for_meraki.py

## files 
## 


