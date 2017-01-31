# DNSmasq

## Install
> `brew install dnsmasq`  

## Configure
To configure dnsmasq, copy the example configuration to `/usr/local/etc/dnsmasq.conf` and edit to taste.

> `cp /usr/local/opt/dnsmasq/dnsmasq.conf.example /usr/local/etc/dnsmasq.conf`  

To have launchd start dnsmasq and restart at startup:

> `sudo brew services start dnsmasq`  


- - - -

## Sample Config
```
address=/gateway.rxf.io/10.9.8.1
address=/esxi.io.lan/10.9.8.10
address=/esxi1.io.lan/10.9.8.10
address=/esxi2.io.lan/10.9.8.11
address=/esxi3.io.lan/10.9.8.12
address=/esxi4.io.lan/10.9.8.13
address=/vcenter.io.lan/10.9.8.20
address=/opsmgr.io.lan/10.9.8.30
address=/.run.io/10.9.8.40
address=/.run.com/10.9.8.40
address=/.apps.io/10.9.8.40
address=/.apps.com/10.9.8.40
address=/.wildcardtest.io/10.9.8.1
```



#km/networking