###  tcp.flags == 0x002 
#### In Wireshark (or tshark) means you are filtering for TCP packets with only the SYN flag set
TCP flags are bit values:
FIN = 0x01
SYN = 0x02
RST = 0x04
PSH = 0x08
ACK = 0x10
URG = 0x20
ECE = 0x40
CWR = 0x80

###  tcp.flags == 0x012
#### Combine  SYN and ACK which is used for port scan identify.

### Nmap scan result

tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024

#### why the above command useful:
 -> Only detect initial connect ( 1st step of  3-ways handshake)
 -> Larger window size which is abnormal means attack or scan

### Open port in destination in range
udp.dstport in {55 .. 70} 


### List all the unique user-agent 
tshark -r version.pcapng -Y "http.request" -T fields -e http.user_agent | sort -u
