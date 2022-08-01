## Networking tool - Trace Route
Traceroute can be used to map the path your request takes as it heads to the target machine.

The internet is a large and complex aggregation of network hardware, connected together by gateways. Traceroute allows you to see each of these connections, it allows you to see every intermediate step between your computer and the resource that you requested.

Tracking the route one's packets follow (or finding the miscreant gateway that's discarding your packets) can be difficult. Traceroute utilizes the IP protocol 'time to live' field and attempts to elicit an ICMP TIME_EXCEEDED response from each gateway along the path to some host. The only mandatory parameter is the destination host name or IP number.
The default probe datagram length is 40 bytes, but this may be increased by specifying a packet size (in bytes) after the destination host name.
     
The basic syntax for traceroute on Linux is this: traceroute google.com

## Notable option
### -e    

Firewall evasion mode, use fixed destination ports for UDP and TCP probes. The destination port does *not* increment with each packet sent.

For a complete list of all available options reference the manual page for traceroute: man traceroute.
     
This program is intended for use in network testing, measurement and management. It should be used primarily for manual fault isolation. Because of the load it could impose on the network, it is unwise to use traceroute during normal operations or from automated scripts.

Example:

     [yak 71]% traceroute nis.nsf.net.
     traceroute to nis.nsf.net (35.1.1.48), 64 hops max, 38 byte packet
     1  helios.ee.lbl.gov (128.3.112.1)  19 ms  19 ms  0 ms
     2  lilac-dmc.Berkeley.EDU (128.32.216.1)  39 ms  39 ms  19 ms
     3  lilac-dmc.Berkeley.EDU (128.32.216.1)  39 ms  39 ms  19 ms
     4  ccngw-ner-cc.Berkeley.EDU (128.32.136.23)  39 ms  40 ms  39 ms
     5  ccn-nerif22.Berkeley.EDU (128.32.168.22)  39 ms  39 ms  39 ms
     6  128.32.197.4 (128.32.197.4)  40 ms  59 ms  59 ms
     7  131.119.2.5 (131.119.2.5)  59 ms  59 ms  59 ms
     8  129.140.70.13 (129.140.70.13)  99 ms  99 ms  80 ms
     9  129.140.71.6 (129.140.71.6)  139 ms  239 ms  319 ms
     10  129.140.81.7 (129.140.81.7)  220 ms  199 ms  199 ms
     11  nic.merit.edu (35.1.1.48)  239 ms  239 ms  239 ms

Note that lines 2 & 3 are the same. This is due to a buggy kernel on the 2nd hop system - lbl-csam.arpa - that forwards packets with a zero ttl (a bug in the distributed version of 4.3 BSD). Note that you have to guess what path the packets are taking cross-country since the NSFNet (129.140) doesn't supply address-to-name translations for its NSSes.

A more interesting example is:

     [yak 72]% traceroute allspice.lcs.mit.edu.
     traceroute to allspice.lcs.mit.edu (18.26.0.115), 64 hops max
     1  helios.ee.lbl.gov (128.3.112.1)  0 ms  0 ms  0 ms
     2  lilac-dmc.Berkeley.EDU (128.32.216.1)  19 ms  19 ms  19 ms
     3  lilac-dmc.Berkeley.EDU (128.32.216.1)  39 ms  19 ms  19 ms
     4  ccngw-ner-cc.Berkeley.EDU (128.32.136.23)  19 ms  39 ms  39 ms
     5  ccn-nerif22.Berkeley.EDU (128.32.168.22)  20 ms  39 ms  39 ms
     6  128.32.197.4 (128.32.197.4)  59 ms  119 ms  39 ms
     7  131.119.2.5 (131.119.2.5)  59 ms  59 ms  39 ms
     8  129.140.70.13 (129.140.70.13)  80 ms  79 ms  99 ms
     9  129.140.71.6 (129.140.71.6)  139 ms  139 ms  159 ms
     10  129.140.81.7 (129.140.81.7)  199 ms  180 ms  300 ms
     11  129.140.72.17 (129.140.72.17)  300 ms  239 ms  239 ms
     12  * * *
     13  128.121.54.72 (128.121.54.72)  259 ms  499 ms  279 ms
     14  * * *
     15  * * *
     16  * * *
     17  * * *
     18  ALLSPICE.LCS.MIT.EDU (18.26.0.115)  339 ms  279 ms  279 ms

Note that the gateways 12, 14, 15, 16 & 17 hops away either don't send ICMP "time exceeded" messages or send them with a ttl too small to reach us. 14 - 17 are running the MIT C Gateway code that doesn't send "time exceeded". God only knows what's going on with 12. 

The silent gateway 12 in the above may be the result of a bug in the 4.[23] BSD network code (and its derivatives): 4.x (x <= 3) sends an unreachable message using whatever ttl remains in the original datagram. Since, for gateways, the remaining ttl is zero, the ICMP "time exceeded" is guaranteed to not make it back to us. The behavior of this bug is slightly more interesting when it appears on the destination system:

     1  helios.ee.lbl.gov (128.3.112.1)  0 ms  0 ms  0 ms
     2  lilac-dmc.Berkeley.EDU (128.32.216.1)  39 ms  19 ms  39 ms
     3  lilac-dmc.Berkeley.EDU (128.32.216.1)  19 ms  39 ms  19 ms
     4  ccngw-ner-cc.Berkeley.EDU (128.32.136.23)  39 ms  40 ms  19 ms
     5  ccn-nerif35.Berkeley.EDU (128.32.168.35)  39 ms  39 ms  39 ms
     6  csgw.Berkeley.EDU (128.32.133.254)  39 ms  59 ms  39 ms
     7  * * *
     8  * * *
     9  * * *
     10  * * *
     11  * * *
     12  * * *
     13  rip.Berkeley.EDU (128.32.131.22)  59 ms !  39 ms !  39 ms !
     
Notice that there are 12 "gateways" (13 is the final destination) and exactly the last half of them are "missing". What's really happening is that rip (a Sun-3 running Sun OS3.5) is using the ttl from our arriving datagram as the ttl in its ICMP reply. So, the reply will time out on the return path, (with no notice sent to anyone since ICMP's aren't sent for ICMP's) until we probe with a ttl that's at least twice the path length. 

I.e., rip is really only 7 hops away, a reply that returns with a ttl of 1 is a clue this problem exists. Traceroute prints a "!" after the time if the ttl is <= 1. Since vendors ship a lot of obsolete (DEC's Ultrix, Sun 3.x) or non-standard (HPUX) software, expect to see this problem frequently and/or take care picking the target host of your probes.     
     
Other possible annotations after the time are !H, !N, or !P (host, network or protocol unreachable), !S (source route failed), (fragmentation needed - the RFC1191 Path MTU Discovery value is displayed), !U or !W (destination network/host unknown), !I (source host is isolated), !A (communication with destination network administratively prohibited), !Z (communication with destination host administratively prohibited), !Q (for this ToS the destination network is unreachable), !T (for this ToS the destination host is unreachable), !X (communication administratively prohibited), !V (host precedence violation), !C (precedence cutoff in effect), or !<num> (ICMP unreachable code <num>). 

These are defined by RFC1812 (which supersedes RFC1716). If almost all the probes result in some kind of unreachable, traceroute will give up and exit.    




