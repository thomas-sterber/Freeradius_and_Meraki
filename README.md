# Using Freeradius for Meraki on Debian based systems , Raspian

This guide is to easily setup a Freeradius in your lab which can be used as a AAA for a Meraki environment.

## Tested setups

### MR (802.1X, MAB)

<table>
<tr><th>802.1X </th><th>MAB</th></tr>
<tr><td>

| authentication                    | tested | 
| --------------------------------  | ------ |
| 802.1X                            | yes | 
| 802.1X and vlan assignment        | yes |
| 802.1X and GroupPolicy assignment | yes |

</td><td>

| authentication                    | tested | 
| --------------------------------  | ------ |
| MAB                               | yes |
| MAB and vlan assignment           | yes |
| MAB and GroupPolicy assignment    | yes |

</td></tr> </table>


### MS (802.1X, MAB)

<table>
<tr><th>802.1X </th><th>MAB</th></tr>
<tr><td>

| authentication                    | tested | 
| --------------------------------  | ------ |
| 802.1X                            | yes | 
| 802.1X and vlan assignment        | yes |
| 802.1X and GroupPolicy assignment | yes |

</td><td>

| authentication                    | tested | 
| --------------------------------  | ------ |
| MAB                               | yes |
| MAB and vlan assignment           | yes |
| MAB and GroupPolicy assignment    | yes |

</td></tr> </table>


### MX  (802.1X)

| authentication      | tested |
| ------------------- | ------ |
| 802.1X              | yes    |


### Adaptive Policy SGT assignment

| device | authentication                  | tested |
| ------ | ------------------------------- | ------ |
| MS390  | 802.1X and SGT assignment       | no     |
| MS390  | MAB  and SGT assignment         | no     |
|        |                                 |        |
| MR55   | 802.1X and SGT assignment       | no     |
| MS55   | MAB  and SGT assignment         | no     |



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


