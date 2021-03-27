# AX25-Openwrt

AX.25 packages for Openwrt -- ax25-tools and libax25. 

I use them to do IP-based wireless mesh networking with [batmand](https://www.open-mesh.org/projects/batmand/wiki)  (Layer 3 version of the B.A.T.M.A.N. mesh protocol - IPv4 only) with HC-12 serial RF transceiver modules attached to serial ports of WiFi routers.

At the moment, AX.25 kernel support has to be added manually using the *make kernel_menuconfig* command inside the Openwrt build environment.

Choose *Networking support*

Choose *Amateur Radio support*

Select *Amateur Radio AX.25 Level 2 protocol*

Select *AX.25 network device drivers*

For HC-12 or similar serial modules, select *Serial port Kiss driver*.

Disable the serial TTY console line in inittab, like this:
	
	::sysinit:/etc/init.d/rcS S boot
	::shutdown:/etc/init.d/rcS K shutdown
	#::askconsole:/usr/libexec/login.sh
  
Restart *init* or reboot.
	
Edit AX.25 configuration in */etc/ax25/axports* for callsign, baud rate and so on.

Bring the interface up with the *kissattach* command. If you want to do mesh networking, enable broadcasts. 

All radio transmissions are broadcasts anyway ;)

Happy AX.25 networking / meshing!
