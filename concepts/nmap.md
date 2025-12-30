## Nmap:
- used to gain information over the network about the hosts , ports and services running
- ping stands for packet internet proofer
## Commands for nmap:
- -sn for ping(host up, mac addr)
- -Pn is a switch if the ping probes are being dropped by the server.(doesnt send icmp packets)
- -sn --traceroute FQDN
- --dns-servers '1.1.1.1' (change the dns server to resolve the query)
- -n (dont resolve the dns name)
- -p portnumber ip
- -p- for all 65535 ports
- -sT for tcp ports
- -sU for udp ports
- 192.168.128.*
- -iL listname
- -iR all the network
- -e interface name
- -sV forr the version of  the service
- -sV --version-intensity 0~9
- -O for operating system
- --osscan-guess
- -6 for  ipv6
- 

# if we have firewall up to evade firewall we can use ARP
- we will send a particular arp request to the victim and in return it will send the mac address meaning that it is in on state and responding on the internet
- we can use switches '-sn ip -PR'
## More things i learnt during this session:
- hop on the router stand for host of/on the point
- passive os fingerprinting and banner grabbing - (linux -ttl =64, window size=5840) (windows -ttl =128, window size=8192) (cisco router -ttl =255, window size=4128)