## Identifying devices on a network.
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

