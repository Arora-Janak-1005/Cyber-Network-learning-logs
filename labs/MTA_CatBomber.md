## SCENARIO

LAN segment data:

- LAN segment range:  10.5.28[.]0/24 (10.5.28[.]0 through 10.5.28[.]255)
- Domain:  catbomber[.]net
- Domain controller:  10.5.28[.]8 - Catbomber-DC
- LAN segment gateway:  10.5.28[.]1
- LAN segment broadcast address:  10.5.28[.]255

## QUESTIONS
[[CatBomber_report]]
#trickbot_mal
This month's pcap is a Trickbot infection in an Active Directory (AD) environment where the infection spreads to the Domain Controller (DC).

- Based on the Trickbot infection's HTTP POST traffic, what is the IP address, host name, and user account name for the infected Windows client?
- What is the other user account name and other Windows client host name found in the Trickbot HTTP POST traffic?
- What is the infected user's email password?
- Two Windows executable files are sent in the network traffic.  What are the SHA256 file hashes for these files?
# First learn:
- look at the dns, what kind of traffic is being asked .(like if a pcap has a where is my ip , that will be strange because why would a normal everyday userr want to check what public ip am i on but a botnet or a trickbot will because the bot has to see what am i contacting the attacker with with , what am i attaching too)
- Go look for low hanging fruit like the http requests because the tech now a days mostly dont use http they use https, and we want to see where the data is going, what websites am i visiting.
- follow the tcp stream.
the http post 1:
- we can see now the normal format of the what we should be seeing
- another thing to cause alae\rm is the host field : here the host field
shows n ip whereas it should show a domain anme like youtube or what ever .
- also things to look at is the kind of stuff we are posting, here we are giving information of cards,bills,etc
- also we can see the server as cowboy.
---
# we look up the geoip of the server to know where our data is actually going to.
follow the link in the tutorial video for the geoip in wireshark enable
---
# we can actually se the file that is being asked by these by going to export and then go to service like http and then see what is being asked by which ip and so here papr.png is being asked
now ***DO NOT EXPORT THESE FILES ARE REAL MALWARES***
 *wireshark command 'frame contains imgpaper'*
# JA3 fullstring
- in the client hello in the very beginning of the pcap , we can see the options in this string 
these are the extended options available ,which can be scanned and we can prepare an output 
- each client hello has a signature and we can fingerprint the type of application that is sending this particular type of hello
based on the options that are sent, we look at versions, ports ,cypher suites and extensions.
the JA3 given below is the md5 hash, you can go online on {ja3er.com}
- we can see the signature of what kind of attack or virus is used


---
# References:
- malware-traffic-analysis.net : https://malware-traffic-analysis.net/2020/05/28/index.html
- chris greer yt channel: https://youtu.be/Brx4cygfmg8?si=lTqGUnHwNQilt5z7
---
