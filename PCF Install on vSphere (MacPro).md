# PCF Install on MacPro

## Remote Access 
Two user accounts are configured:
* vm:P!votal1 
> Used for long running system processes, such as the underlying vSphere ESXI hosts in isolation and other long running processes like DNSmasq, IP updater, etc.  Should not be logged out.  
* pcf:P!votal1
> Used for running short running processes, such as vSphere vCenter, vCenter Mgmt console, ESXI host consoles, and PCF admin consoles like Ops Manager and Apps Manager, etc.  

### SSH
```
dns-sd -E  

10832270356 (pivotal.vm@icloud.com)
10827989305 (pivotal.pcf@icloud.com)
10623758365 (pivotal.ninja@icloud.com)

# Direct SSH

ssh -2 -6 vm@banzai.1072716341.members.btmm.icloud.com
ssh -2 -6 pcf@banzai.1072716341.members.btmm.icloud.com
ssh -2 -6 farmer@banzai.1072716341.members.btmm.icloud.com
ssh -2 -6 farmer@mac.1072716341.members.btmm.icloud.com
```

### Chrome Remote Desktop

**Users**
* pivotal.vm@gmail.com:P!votal1
* pivotal.pcf@gmail.com:P!votal1

Note: only one of these may be open at a time and it must be initiated via the full remote access VNC accounts that run locally on the system

## DNS
Local DNS is handled using DNSmasq

### Install
> `brew install dnsmasq`  

### Configure
To configure dnsmasq, copy the example configuration to `/usr/local/etc/dnsmasq.conf` and edit to taste.

> `cp /usr/local/opt/dnsmasq/dnsmasq.conf.example /usr/local/etc/dnsmasq.conf`  

To have launchd start dnsmasq and restart at startup:

> `sudo brew services start dnsmasq`  

- - - -

### Sample Config
```
address=/gateway.rxf.io/10.9.8.1
address=/esxi.lan/10.9.8.10
address=/esxi1.lan/10.9.8.10
address=/esxi2.lan/10.9.8.11
address=/esxi3.lan/10.9.8.12
address=/esxi4.lan/10.9.8.13
address=/vcenter.lan/10.9.8.20
address=/opsmgr.lan/10.9.8.30
address=/.run.rxf.io/10.9.8.40
address=/.apps.rxf.io/10.9.8.40
address=/.wildcardtest.lan/10.9.8.1
```



## ESXI
### Configuration
Each host should be configured with the following:

* 48Gb RAM
* 2Tb Disk
* Network









#km/install-vsphere