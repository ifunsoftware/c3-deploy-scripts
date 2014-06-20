c3-deploy-scripts
=================

C3 deployment configuration

You need to have Capistrano v3 installed in your system:
http://capistranorb.com/documentation/getting-started/installation/

You also need to update your .ssh/config file to configure ssh proxy for node0 and node1

```
Host plab
HostName plabrouter.ifunsoftware.com
User routeradmin
Port 212

Host node0.c3.ifunsoftware.com
HostName 192.168.1.109
User aphreet
ProxyCommand  ssh plab netcat -w 120 %h %p 

Host node1.c3.ifunsoftware.com
HostName 192.168.1.112
User aphreet
ProxyCommand  ssh plab netcat -w 120 %h %p
```

Make sure you can ssh to plab with keys

Get all supported tasks:

```
#> cd c3/
#> cap -T
```
