## Networking tool - ping
The ping utility uses the ICMP (Internet Control Message Protocol) protocol's mandatory ECHO_REQUEST datagram to elicit an ICMP ECHO_RESPONSE from a host or gateway.  
ECHO_REQUEST datagrams (pings) have an IP and ICMP header, followed by a struct timeval and then an arbitrary number 
of pad bytes used to fill out the packet.
## Ping commands - man ping for help menu.

### -v      
Verbose output.  ICMP packets other than ECHO_RESPONSE that are received are listed.

```Shell
MacBook-Pro-2% ping -v -c 4 google.com
PING google.com (142.250.72.142): 56 data bytes
64 bytes from 142.250.72.142: icmp_seq=0 ttl=119 time=70.645 ms
64 bytes from 142.250.72.142: icmp_seq=1 ttl=119 time=122.099 ms
64 bytes from 142.250.72.142: icmp_seq=2 ttl=119 time=91.561 ms
64 bytes from 142.250.72.142: icmp_seq=3 ttl=119 time=70.412 ms

--- google.com ping statistics ---
4 packets transmitted, 4 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 70.412/88.679/122.099/21.119 ms
MacBook-Pro-2%
```
             
### Control+C 
Stop a ping request.  

```Shell
MacBook-Pro-2% ping google.com
PING google.com (142.250.72.142): 56 data bytes
64 bytes from 142.250.72.142: icmp_seq=0 ttl=119 time=73.867 ms
64 bytes from 142.250.72.142: icmp_seq=1 ttl=119 time=125.160 ms
^C
--- google.com ping statistics ---
2 packets transmitted, 2 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 73.867/99.513/125.160/25.647 ms
MacBook-Pro-2% 
```
 ### -c count
 
 Stop after sending (and receiving) count ECHO_RESPONSE packets.
 If this option is not specified, ping will operate until interrupted.  
 If this option is specified in conjunction with ping sweeps, each sweep will consist of count packets.
 
```Shell             
MacBook-Pro-2% ping -c 4 google.com
PING google.com (142.250.72.142): 56 data bytes
64 bytes from 142.250.72.142: icmp_seq=0 ttl=119 time=80.067 ms
64 bytes from 142.250.72.142: icmp_seq=1 ttl=119 time=68.594 ms
64 bytes from 142.250.72.142: icmp_seq=2 ttl=119 time=69.153 ms
64 bytes from 142.250.72.142: icmp_seq=3 ttl=119 time=72.990 ms

--- google.com ping statistics ---
4 packets transmitted, 4 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 68.594/72.701/80.067/4.577 ms
MacBook-Pro-2% 
```

### -f 

*Flood ping.*  

Outputs packets as fast as they come back or one hundred times per second, whichever is more. For every ECHO_REQUEST sent a period "." is printed, while for every ECHO_REPLY received a backspace is printed. This provides a rapid display of how many packets are being dropped.  Only the super-user may use this option. 

*This can be very hard on a network and should be used with caution.*
