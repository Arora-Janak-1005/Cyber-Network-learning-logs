## Security Bypass Techniques
- we are by bypassing security devices like ids, ips ,firewalls ,antivirus
- we are using wireshark for this
## Syn Stealth Scan:
- this type of scan is either done by using sudo along with nmap scan or use -sS switch for this.
- what it does is that is different than a normal scan is that a normal scan uses tcp handshake , in this scan when the client sends a syn the server replies syn,ack and then then clients resets it.
- if we recieve syn,ack then the port is open ,if rst then closed if none then firewall.
- cristmas scan -sX
- -sN for none packets or empty packets
## mac spoofing for evasion:
- --spoof-mac 0(rand)
- --spoof-mac dell
## Decoy scan:
- using multiple different ips to  bypass firewall, using different ips wont get us blocked (using in the env ips will help bypass firewall since it will think of insider)
- sudo nmap -sS -D RND:2 ip
- sudo nmap -sS -D 1.1.1.1,2.2.2.2 ip
## manipulation of mtu size and fragments:
- sudo nmap --mtu 16(8 multiplier) ip
- -f for fragment
## zombie scan:
- use vulnerable machines in a network to bypass the firewall (nmap from a vuln machine) but to do that we must first find a vulnerable machine in the network.
- sudo nmap -sI idleip targetip port 