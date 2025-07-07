#Update:
Tango has recently been reaching out to NS providers and moving them to a new server configuration that is supposed to mitigate this issue. At this time, I'm not planning on working on this anymore, as it seem to no longer be needed. 





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
```
rm -rf /etc/kamailio
mkdir /etc/kamailio
git clone https://github.com/skels130/Tango-NS-Proxy.git /etc/kamailio/
```
3. Make kamailio-local.cfg
```
touch /etc/kamailio-local.cfg
```
Edit /etc/kamailio/kamailio-local.cfg with the following lines, putting in your server information where needed for *IP ADDRESS* and *FQDN*. You can also change the ports as desired. 
```
listen=tcp:*IP ADDRESS*:5060;
listen=udp:*IP ADDRESS*:5060;
# listen=tcp:*IP ADDRESS*:8080; # can be used for JSONRPC to control kamailio with additional config
# listen=tls:*IP ADDRESS*:8081; # can be used for JSONRPC to control kamailio with additional config
alias="*FQDN*";

```
