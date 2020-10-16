# Using Freeradius for Meraki on Debian based systems , Raspian

This guide is to easily setup a Freeradius which can be used as a AAA for a Meraki authentication tests in your LAB or POC.

## installation instructions

### preparation of Raspian
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

### Meraki Wireless   (MR)

<table>
<tr><th>802.1X </th><th>MAB</th></tr>
<tr><td>

| authentication                    | supported | 
| --------------------------------  | ------ |
| 802.1X                            | yes | 
| 802.1X and vlan assignment        | yes |
| 802.1X and GroupPolicy assignment | yes |

</td><td>

| authentication                    | supported | 
| --------------------------------  | ------ |
| MAB                               | yes |
| MAB and vlan assignment           | yes |
| MAB and GroupPolicy assignment    | yes |

</td></tr> </table>


### Meraki Switching  (MS)

<table>
<tr><th>802.1X </th><th>MAB</th></tr>
<tr><td>

| authentication                    | supported | 
| --------------------------------  | ------ |
| 802.1X                            | yes | 
| 802.1X and vlan assignment        | yes |
| 802.1X and GroupPolicy assignment | yes |

</td><td>

| authentication                    | supported | 
| --------------------------------  | ------ |
| MAB                               | yes |
| MAB and vlan assignment           | yes |
| MAB and GroupPolicy assignment    | yes |

</td></tr> </table>


### Meraki Security Appliance  (MX)

<table>
<tr><th>802.1X </th></tr>
<tr><td>
  
| device              | supported |
| ------------------- | ------ |
| MX65                | yes    |

</td></tr> </table>


### Adaptive Policy SGT assignment

| device | authentication                  | supported |
| ------ | ------------------------------- | ------ |
| MS390  | 802.1X and SGT assignment       | no     |
| MS390  | MAB  and SGT assignment         | no     |
|        |                                 |        |
| MR55   | 802.1X and SGT assignment       | no     |
| MS55   | MAB  and SGT assignment         | no     |





