## Networking tool - Trace Route
Traceroute can be used to map the path your request takes as it heads to the target machine.

The internet is a large and complex aggregation of network hardware, connected together by gateways. Traceroute allows you to see each of these connections, it allows you to see every intermediate step between your computer and the resource that you requested.

Tracking the route one's packets follow (or finding the miscreant gateway that's discarding your packets) can be difficult. Traceroute utilizes the IP protocol `time to live' field and attempts to elicit an ICMP TIME_EXCEEDED response from each gateway along the path to some host. The only mandatory parameter is the destination host name or IP number.
The default probe datagram length is 40 bytes, but this may be increased by specifying a packet size (in bytes) after the destination host name.
     
The basic syntax for traceroute on Linux is this: traceroute <destination>
