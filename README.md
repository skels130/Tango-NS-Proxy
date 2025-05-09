# Tango-NS-Proxy
A Proxy to sit between Netsapiens servers and Tango's Mobile-X servers to fix contact IP issues.


1. Installing Kamailio on Ubuntu
    Instructions: https://deb.kamailio.org/
   --or--
    Run the following:

```
wget -O- http://deb.kamailio.org/kamailiodebkey.gpg | apt-key add -
```
   
```
tee /etc/apt/sources.list.d/kamailio.list<<EOF
deb     http://deb.kamailio.org/kamailio60 noble main
deb-src http://deb.kamailio.org/kamailio60 noble main
EOF 
```
```
sudo apt update
```
```
sudo apt install kamailio kamailio-mysql-modules kamailio-tls-modules kamailio-utils-modules
```
2. Configure this git repo, or copy config to existing file:


