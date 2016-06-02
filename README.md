# tasker-weasel
Tasks and profiles for Tasker

Of course, these all require [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=en).

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

![example](example.png?raw=true "With wifi enabled")