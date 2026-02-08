# 1.General Format:
field operator value

## 2. Core Operators

| Operator | Meaning |
|---------|--------|
| `==` | Equal |
| `!=` | Not equal |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater or equal |
| `<=` | Less or equal |
| `&&` | AND |
| `||` | OR |
| `!` | NOT |
| `contains` | Substring match |
| `matches` | Regex match |

---

## 3. IP & Network Filters

- `ip` — all IPv4 traffic  
- `ip.addr == 192.168.1.1` — traffic to or from this IP  
- `ip.src == 10.0.0.5` — traffic from this source IP  
- `ip.dst == 8.8.8.8` — traffic to this destination IP  
- `ipv6` — all IPv6 traffic  


---

## TCP / UDP Filters

- `tcp` — all TCP packets  
- `udp` — all UDP packets  
- `tcp.port == 80` — TCP traffic on port 80  
- `udp.port == 53` — UDP traffic on port 53 (DNS)  
- `tcp.srcport == 443` — source port 443  
- `tcp.dstport == 22` — destination port 22 (SSH)  

---

## Protocol Filters

- `http` — HTTP traffic  
- `https` — HTTPS traffic  
- `dns` — DNS queries and responses  
- `ftp` — FTP traffic  
- `ssh` — SSH traffic  
- `icmp` — ICMP (ping)  
- `arp` — ARP packets  
- `dhcp` — DHCP traffic  
- `tls` — TLS handshakes and sessions  
- `smtp` — Email (SMTP)  
- `pop` — POP3  
- `imap` — IMAP  
- `ntp` — Network Time Protocol  
- `snmp` — SNMP management traffic  

---

## HTTP Filters

- `http.request` — only HTTP requests  
- `http.response` — only HTTP responses  
- `http.request.method == "GET"` — GET requests  
- `http.request.method == "POST"` — POST requests  
- `http.host contains "google"` — requests to google  
- `http.user_agent` — show User-Agent field  

---

## DNS Filters

- `dns` — all DNS traffic  
- `dns.qry.name == "example.com"` — query for domain  
- `dns.flags.response == 1` — DNS responses only  
- `dns.flags.response == 0` — DNS queries only  

---

## ICMP (Ping)

- `icmp` — all ICMP packets  
- `icmp.type == 8` — echo request (ping)  
- `icmp.type == 0` — echo reply  

---

## Follow Conversations

- `tcp.stream == 0` — show only TCP stream 0  
- `udp.stream == 2` — show only UDP stream 2  

---

## String / Content Matching

- `frame contains "password"` — packets containing word  
- `frame contains "admin"` — packets containing admin  
- `http.host contains "facebook"` — Facebook traffic  
- `http.host matches "(?i)google"` — regex, case-insensitive  

---

## Error & Performance Analysis

- `tcp.analysis.retransmission` — retransmitted packets  
- `tcp.analysis.duplicate_ack` — duplicate ACKs  
- `tcp.flags.reset == 1` — TCP resets  
- `_malformed` — malformed packets  

---

## Security / Pentesting

- `http.authorization` — HTTP auth headers  
- `ftp.request.command == "PASS"` — FTP passwords  
- `tcp.flags.syn == 1 && tcp.flags.ack == 0` — SYN scan  
- `dns && !(dns.qry.name contains "google")` — suspicious DNS  
- `arp.duplicate-address-detected` — ARP spoofing  
- `ssh && frame contains "failed"` — SSH brute force  

---

## Broadcast / Multicast

- `eth.dst == ff:ff:ff:ff:ff:ff` — Ethernet broadcast  
- `ip.dst == 255.255.255.255` — IP broadcast  

---

## Time-Based Filters

- `frame.time_relative < 10` — first 10 seconds  
- `frame.time_delta > 1` — packets with >1s delay  

---

## Must-Memorize Core Set

- `ip.addr == x.x.x.x` — host filter  
- `tcp.port == 80` — HTTP  
- `dns` — DNS  
- `http` — HTTP  
- `tcp.stream == n` — follow session  
- `tcp.analysis.retransmission` — network issues  
- `frame contains "string"` — content search  

---

## Mental Model

- Capture filters → Firewall rules  
- Display filters → SQL WHERE clause  

Equivalent concept:

`SELECT * FROM packets WHERE condition;`

---
End of Document
