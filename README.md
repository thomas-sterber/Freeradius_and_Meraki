# Using Freeradius for Meraki on Debian based systems , Raspian

This guide is to easily setup a Freeradius in your lab which can be used as a AAA for a Meraki environment.

## Tested setups

### MR (802.1X, MAB)

<table>
<tr><th>802.1X </th><th>MAB</th></tr>
<tr><td>

| authentification                  | tested | 
| --------------------------------  | ------ |
| 802.1X                            | yes | 
| 802.1X and vlan assignment        | yes |
| 802.1X and GroupPolicy assignment | yes |

</td><td>

| authentification                  | tested | 
| --------------------------------  | ------ |
| MAB                               | yes |
| MAB and vlan assignment           | yes |
| MAB and GroupPolicy assignment    | yes |

</td></tr> </table>


### MS (802.1X, MAB)

| authentification                          | tested |
| ----------------------------------------  | ------ |
| 802.1X                                    | yes    |
| 802.1X and vlan assignment                | no     | 
| 802.1X and AccessGroupPolicy assignment   | no     |   

### MX  (802.1X)

| authentification    | tested |
| ------------------- | ------ |
| 802.1X              | yes    |


### Adaptive Policy SGT assignment

| authentification                  | tested |
| --------------------------------- | ------ |
| SGT assignment                    | no     |
| SGT and GroupPolicy assignment    | no     |



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


