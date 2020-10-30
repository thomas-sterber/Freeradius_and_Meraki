# Using Freeradius for Meraki on Raspberry

This guide is to easily setup a Freeradius which can be used as a AAA for a Meraki authentication tests in your Lab or POC.

## Meraki_Freeradius_UI
in work

## Testmatrix


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



## Freeradius installation instructions

### Raspberry Pi setup
    please have a look @ https://github.com/thomas-sterber/Setup_Raspberry_without_mouse_and_keyboard
    

### Freeradius for Meraki configs

#### Install Freeradius

        #sudo apt-get update
        #sudo apt-get dist-upgrade
        #sudo apt-get install freeradius
        #sudo apt-get install freeradius-utils

#### Freeradius start/stop/autostart , Debug mode

        Check Freeradius service
	    #sudo service freeradius status
	    #pgrep freeradius

        Stop service also disable autostart after boot
	    #sudo service freeradius stop

        Start service also enable autostart after reboot
	    #sudo service freeradius start
        Start in Debug Mode
	    # sudo service freeradius stop
	    # sudo freeradius -X

#### Basic Freeradius Configuration

        ssh to the Raspberry and login.     (pi/meraki123)
        >> Backup/move/clear orgiginal configs files
 
	    #mkdir freeradius_backup
	    #cd freeradius_backup
	    #sudo su
	    #cp /etc/freeradius/3.0/users .
	    #> /etc/freeradius/3.0/users
	    #cp /etc/freeradius/3.0/clients.conf .
	    #> /etc/freeradius/3.0/clients.conf
	    #cp /etc/freeradius/3.0/radiusd.conf .
	    #cp /etc/freeradius/3.0/mods-available/eap . 
	    #exit
        
        >> modify config-files

	        #sudo vim /etc/freeradius/3.0/mods-available/eap
         		    change two time 'use_tunneled_reply' to 'yes'
        		    (EAP-TTLS section and EAP-PEAP section)
        		    This allows to configure the radius attributes direct in 'users'
	            use_tunneled_reply = yes    

            	#sudo vim /etc/freeradius/3.0/radiusd.conf
                	change 'name = freeradius' to 'name = meraki-freeradius'

#### Test your Freeradius Server

	#sudo vim /etc/freeradius/3.0/clients.conf
	
		client localhost {
			  ipaddr = 127.0.0.1
			  secret  = secret123
				   }

	#sudo vim /etc/freeradius/3.0/users

		thomas		Cleartext-Password := "sterber"


	#sudo freeradius -X      (terminal 1)
	#radtest thomas sterber 127.0.0.1 0 secret123      (terminal 2)
			(user) (pwd) (server ip) (NAS Port) (secret)


#### Configure Freeradius 'clients.conf'

	#sudo vim /etc/freeradius/3.0/clients.conf

	Trust all incoming requests (best practice for Lab environments)
		client all {
			ipaddr		= 0.0.0.0/0
			secret		= secret123
			}


#### Configure Freeradius 'users'

##### MAB	(MR, MS and MX)

		a45046d55355		Cleartext-Password := "a45046d55355"
		
		
##### MAB + VLAN 	(MR and MS)

		9829a642667c		Cleartext-Password := "9829a642667c"
					Tunnel-Medium-Type = 6,
					Tunnel-Private-Group-ID = 10,
					Tunnel-Type = VLAN


##### MAB + GroupPolicy 

		e82a44a133c1		Cleartext-Password := "e82a44a133c1"
					Filter-ID := GroupPolicy_01



