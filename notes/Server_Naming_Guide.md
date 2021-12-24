# PROPER SERVER NAMING SCHEME  
<Ref: https://mnx.io/blog/a-proper-server-naming-scheme/>  

## A Records  
`crimson.example.com.   A   192.0.2.11` 

## CNAME Records  
The CNAME records are what developers should know and use for interconnecting services.
Start with your registered domain, and segment each piece of additional information as a proper subdomain going down from there.  
DNS is hierarchical by design, so taking advantage of that will provide us with some benefits later on.  
Eg:  `<wip>.example.com.   CNAME   crimson.example.com.`

### Specify Environment  
* dev – Development
* tst – Testing
* stg – Staging
* prd – Production

Eg:  `<wip>.prd.nyc.example.com.   CNAME   crimson.example.com.`

### Specify Purpose and Serial Number  
* app – Application Server (non-web)
* sql – Database Server
* ftp – SFTP server
* mta – Mail Server
* dns – Name Server
* cfg – Configuration Management (puppet/ansible/etc.)
* mon – Monitoring Server (nagios, sensu, etc.)
* prx – Proxy/Load Balancer (software)
* ssh – SSH Jump/Bastion Host
* sto – Storage Server
* vcs – Version Control Software Server (Git/SVN/CVS/etc.)
* vmm – Virtual Machine Manager
* web – Web Server

For the serial number, use zero-padded numbers based on your expected capacity. Plan for expansion, but usually two digits will be more than sufficient.  
Eg:  `web01.prd.nyc.example.com.   CNAME   crimson.example.com.`

### Convenience Names  
Eg:  `webmail.example.com.   CNAME   crimson.example.com.`


### Networking and Power Equipment
* con – Console/Terminal Server
* fwl – Firewall
* lbl – Load Balancer (physical)
* rtr – L3 Router
* swt – L2 Switch
* vpn – VPN Gateway
* pdu – Power Distribution Unit
* ups – Uninterruptible Power Supply

## Mail and Name Servers 
For your mail and name servers, you have to utilize DNS A records since MX and NS records must never point to a CNAME alias.  
```
puma.example.com.    A   192.0.2.20
mta01.example.com.   A   192.0.2.20
```

---
# Complete Naming Scheme Example
```
crimson.example.com.         A       192.0.2.11
crimson.lan.example.com.     A       10.0.2.11
crimson.oob.example.com.     A       10.42.2.11
web01.prd.nyc.example.com.   CNAME   crimson.example.com.

melody.example.com.          A       192.0.2.12
melody.lan.example.com.      A       10.0.2.12
melody.oob.example.com.      A       10.42.2.12
web02.prd.nyc.example.com.   CNAME   melody.example.com.

verona.example.com.          A       192.0.2.13
verona.lan.example.com.      A       10.0.2.13
verona.oob.example.com.      A       10.42.2.13
cfg01.prd.nyc.example.com.   CNAME   verona.example.com.
mon01.prd.nyc.example.com.   CNAME   verona.example.com.
puppet.example.com.          CNAME   verona.example.com.
nagios.example.com.          CNAME   verona.example.com.

banjo.example.com.           A       192.0.2.104
banjo.lan.example.com.       A       10.0.2.104
banjo.oob.example.com.       A       10.42.2.104
web01.dev.pdx.example.com.   CNAME   banjo.example.com.
martinlutherkingsr.melblanc.kugupu.stevejob.kenkesey.music.filmhistory.calligraphy.example.com   CNAME   banjo.example.com.
```
