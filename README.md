# tasker-weasel
Tasks and profiles for Tasker

Of course, these all require [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=en).

# Send ICE messages to multiple recipients

Use the text file **icenumbers.txt** to store the phone numbers of your *text* ICE contacts, separated by a | like so:

   15555551212|15556661313|15557771414

then tie either ICE task to an event, and it will send a message to all those contacts with your message and location. The message formats are as follows (where %LOC is replaced by your location and %BATT% replaced by your battery percentage):

**Send_ICE_message.tsk.xml**
I need help. Please call, text, or check on me. 

I am at http://maps.google.com/maps?z=12&t=m&q=loc%LOC

Battery at %BATT%

**Silent_ICE_message.tsk.xml**
I need help. This is a SILENT alert. Call the authorities, not me.  

I am at http://maps.google.com/maps?z=12&t=m&q=loc%LOC

Battery at %BATT%

# Network Login

Ever since Lollipop, I don't get presented with the "need to log in to wifi" prompt.  So this profile and set of tasks will take care of that.

Files:  

**wifi_login.prf**

The profile that is called upon connecting to *any* wifi network

**net.checkip.tsk**

Calls http://checkip.dyndns.org/ .  If the response is *anything* that doesn't make sense, it sets the variable %IPaddy to 0.0.0.0 ; otherwise it will return %IPaddy with the valid address.

**net.logon.tsk**

Calls **checkip** and if the result is 0.0.0.0, launches Chrome, then afterward calls **checkip** again to set the variable properly.

**net.localnet.info.tsk**

Returns the variable %LocalIP which gives you the local IP address of the device and %SSID which gives the SSID of the WiFi network you are connected to. Useful if you've set the particular IP address and want to test that (along with SSID) to see if you want to perform a task, such as connecting to a VPN.

**net.powercycle.tsk**

Powercycles the wifi.

**wifi**

This project provides the usage of *netcfg* and Tasker to check what interface you're using (cell data, wifi, or VPN) and what your local and internet IP addresses are, and provides a task to pass them to [Minimalistic Text](https://play.google.com/store/apps/details?id=de.devmil.minimaltext&hl=en) for a conky-like interface for your Android phone.

The variables returned are:
* %Iface  
* %LocalIP (your IP on the LAN, duh)  
* %SSID (the SSID)  
* %IPaddy (your WAN IP)  

You can see all that is returned from netcfg by (installing a terminal emulator)[https://play.google.com/store/apps/details?id=jackpal.androidterm&hl=en] and simply running netcfg at the prompt.

![example](example.png?raw=true "With wifi enabled")