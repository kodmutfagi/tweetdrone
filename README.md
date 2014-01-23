-*- BiTaksi -*-

Your server needs to connect to Internet and ARDrone at the same time.  ARDrone boots with AdHoc wifi. To switch ARDrone to Wifi Infrastructure mode you must telnet to drone and restart the network :

* First telnet to ARDrone (192.168.1.1)
* Put the following commands into a shell file

	killall udhcpd
	ifconfig ath0 down
	iwconfig ath0 mode managed essid NAMEOFYOURSSID ap any channel auto
	commit
	ifconfig ath0 up
	udhcpc -b -i ath0
 
Run the script.  Be warned that you will disconnect from the drone. You will need to find its new address.
 
  



