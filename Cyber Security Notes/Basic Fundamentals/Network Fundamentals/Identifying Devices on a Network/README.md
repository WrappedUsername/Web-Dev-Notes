# Identifying devices on a network.
<p align="left"> <img src="https://komarev.com/ghpvc/?username=IdentifyingDevicesonaNetwork&label=Repository%20views&color=0e75b6&style=flat" alt="wrappedusername" /> </p>

Devices have, two means of identification, with one being permeable. 

These are:

- An IP Address - IPv4 and IPv6
- A Media Access Control (MAC) Address, similar to a serial number.

## IPv4 Address e.g. 192.168.1.1.
An IPv4 address is a set of numbers that are divided into four octets. 
The value of each octet will be the IP address of the device on the network.

This number is calculated through a technique known as IP addressing & subnetting.
IP addresses can change from device to device but cannot be active simultaneously more than once within the same network.

| Octet 1 | Octet 2 | Octet 3 | Octet 4 |
| --- | --- | --- | --- |
| 192. | 168. | 1. | 1. |
| 0-255 | 0-255 | 0-255 | 0-255 |

IP Addresses follow a set of standards known as protocols. These protocols are the backbone of networking and force many devices to communicate in the same language.

Devices can be on both a private and public network. Depending on where they are, will determine what type of IP address they have, a public or private IP address.
A public address is used to identify the device on the Internet, whereas a private address is used to identify a device amongst other devices.

The table & screenshot below is an example. Here we have two devices on a private network:

| Device Name | IP Address | IP Address Type |
| :---: | :---: | :---: |
| DESKTOP-KJE57FD | 192.168.1.77 | Private | 
| DESKTOP-KJE57FD | 86.157.52.21 | Public | 
| CMNatic-PC | 192.168.1.74 | Private | 
| CMNatic-PC | 86.157.52.21 | Public |

![image](https://user-images.githubusercontent.com/104662990/181930468-4638a16c-6e37-4c84-9207-cb312659084d.png)

These two devices will be able to use their private IP addresses to communicate with each other. However, any data sent to the internet from either of these devices will be identified by the same public IP address.

| Public IPv4 is: 86.157.52.21 |
| :---: |

## IPv6 Address e.g. 2001:0db8:3c4d:0015:0000:0000:1a2f:1a2b
An IPv6 address is 128 bits in length and consists of eight, 16-bit fields, with each field bounded by a colon. Each field must contain a hexadecimal number, in contrast to the dotted-decimal notation of IPv4 addresses. In the next figure, the x's represent hexadecimal numbers.

![image](https://user-images.githubusercontent.com/104662990/181933810-f2310425-b4eb-4392-844f-6088f106ccf0.png)

The leftmost three fields (48 bits) contain the site prefix. The prefix describes the public topology that is usually allocated to your site by an ISP or Regional Internet Registry (RIR).

The next field is the 16-bit subnet ID, which you (or another administrator) allocate for your site. The subnet ID describes the private topology, also known as the site topology, because it is internal to your site.

The rightmost four fields (64 bits) contain the interface ID, also referred to as a token. The interface ID is either automatically configured from the interface's MAC address or manually configured in EUI-64 format.

Example:

| 2001:0db8:3c4d:0015:0000:0000:1a2f:1a2b |
| :---: |

This example shows all 128 bits of an IPv6 address. The first 48 bits, 2001:0db8:3c4d, contain the site prefix, representing the public topology. The next 16 bits, 0015, contain the subnet ID, representing the private topology for the site. The lower order, rightmost 64 bits, 0000:0000:1a2f:1a2b, contain the interface ID.

Base 16 hexadecimal number system - 

IPv6 address has eight, 16 bit fields, 128 bits in total, represented with a hexidecimal number.

MAC address has six, 8 bit fields, 48 bits in total, represented with a hexidecimal number.
| 4 bit Binary Sequence | Hex Representation |
| --- | --- |
| 0000 | 0 |
| 0001 | 1 |
| 0010 | 2 |
| 0011 | 3 |
| 0100 | 4 |
| 0101 | 5 |
| 0110 | 6 |
| 0111 | 7 |
| 1000 | 8 |
| 1001 | 9 |
| 1010 | A |
| 1011 | B |
| 1100 | C |
| 1101 | D |
| 1110 | E |
| 1111 | F |

## Abbreviating IPv6 Addresses

Most IPv6 addresses do not occupy all of their possible 128 bits. This condition results in fields that are padded with zeros or contain only zeros.

The IPv6 addressing architecture allows you use the two-colon (::) notation to represent contiguous 16-bit fields of zeros. For example, you might abbreviate the IPv6 address in the e.g. by replacing the two contiguous fields of zeros in the interface ID with two colons. The resulting address is 2001:0db8:3c4d:0015::1a2f:1a2b. Other fields of zeros can be represented as a single 0. You can also omit any leading zeros in a field, such as changing 0db8 to db8.

So the address 2001:0db8:3c4d:0015:0000:0000:1a2f:1a2b can be abbreviated as 2001:db8:3c4d:15::1a2f:1a2b.

You can use the two colon notation to replace any contiguous fields of all zeros in the IPv6 address. For example, the IPv6 address 2001:0db8:3c4d:0015:0000:d234::3eee:0000 can be collapsed into 2001:db8:3c4d:15:0:d234:3eee::

## MAC Address e.g. a4:c3:f0:85:ac:2d 

A Media Access Control address (MAC address) is a hardware identifier that uniquely identifies each device on a network. Primarily, the manufacturer assigns it. They are often found on a device’s network interface controller (NIC) card. A MAC address can also be referred to as a burned-in address, Ethernet hardware address, hardware address, or physical address.

The MAC address is a 48 bit hexadecimal number, split into six 8 bit fields, separated by a colon. 

For example: a4:c3:f0:85:ac:2d 

The first six characters represent the company that made the network interface, and the last six is a unique number.

Because they are assigned to NIC (network interface controller) or other hardware, MAC addresses never change on their own, but many network interfaces support MAC address changes.

[How to change MAC address](https://www.ibm.com/docs/en/mq-appliance/9.2?topic=commands-mac-address)

In OSI terminology, the MAC sublayer is considered to be a sublayer of the OSI Data Link layer (layer 2). This allows MAC addressing to support other kinds of networks besides TCP/IP.

IP networks manage the conversion between IP and MAC addresses using Address Resolution Protocol (ARP). The Dynamic Host Configuration Protocol (DHCP) relies on ARP to manage the unique assignment of IP addresses to devices.

## 64 bit MAC Address e.g. 00:25:96:12:34:56

Traditional MAC addresses are 48 bits in length, a few types of networks require 64-bit addresses instead. TCP/IP networks based on IPv6 implement a different approach to communicating MAC addresses compared to mainstream IPv4. 

Instead of 64-bit hardware addresses, IPv6 automatically translates a 48-bit MAC address to a 64-bit address by inserting a fixed (hardcoded) 16-bit value FFFE between the vendor prefix and the device identifier. IPv6 calls these numbers identifiers to distinguish them from true 64-bit hardware addresses.

For example, a 48-bit MAC address of 00:25:96:12:34:56 appears on an IPv6 network in either of these two forms:

- 00:25:96:FF:FE:12:34:56
- 0025:96FF:FE12:3456

