# tasker-weasel
Tasks and profiles for Tasker

# Network Login

Ever since Lollipop, I don't get presented with the "need to log in to wifi" prompt.  So this profile and set of tasks will take care of that.

Files:  

**wifi_login.prf**

The profile that is called upon connecting to *any* wifi network


**net.checkip.tsk**

Calls http://checkip.dyndns.org/ .  If the response is *anything* that doesn't make sense, it sets the variable %IPaddy to 0.0.0.0 ; otherwise it will return with the valid address.

**net.logon.tsk**

Calls **checkip** and if the result is 0.0.0.0, launches Chrome, then afterward calls **checkip** again to set the variable properly.

**net.powercycle.tsk**

Powercycles the wifi.


