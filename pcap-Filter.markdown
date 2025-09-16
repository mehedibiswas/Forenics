### 1. tcp.flags == 0x002 
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

### 2. tcp.flags == 0x012
#### Combine  SYN and ACK which is used for port scan identify.



### 3. List all the unique user-agent 
tshark -r version.pcapng -Y "http.request" -T fields -e http.user_agent | sort -u
