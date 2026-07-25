# ComputerNetworks

IP stands for Internet Protocol

An IP Address (Internet Protocol Address) is a unique numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. It serves two main purposes:

Identifying a device on the network.
Locating the device to enable communication with other devices over a network like the Internet.

# There are 2 types of Addressing 

1) Logical (Eg - India , Delhi , Mumbai etc )  IP address ipv4 and ipv6


2) Physical (MAC addressing 48 bit mac address)

If i want to send message from mumbai to norway it is possible with IP

IPV4 - it is 32 bit logical address

##  it has 4 octets each of 8 bit 

# IPv4 Classful Addressing

## IPv4 Address Format (32 bits)

| b7 | b6 | b5 | b4 | b3 | b2 | b1 | b0 | b7 | b6 | b5 | b4 | b3 | b2 | b1 | b0 | b7 | b6 | b5 | b4 | b3 | b2 | b1 | b0 | b7 | b6 | b5 | b4 | b3 | b2 | b1 | b0 |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |    |

| **Octet 1** | **Octet 2** | **Octet 3** | **Octet 4** |
|:-----------:|:-----------:|:-----------:|:-----------:|
| Bits 0–7 | Bits 8–15 | Bits 16–23 | Bits 24–31 |

# IP address is made up of 2 things 

a) network id 

b) host id 


# We have 5 classes for classful addressing

# IPv4 Classful Address Ranges

| Class | First Bits | First Octet Range | IP Address Range | Default Subnet Mask | Purpose |
|:-----:|:----------:|:-----------------:|:----------------:|:-------------------:|:--------|
| A | `0` | ` 0 to 127 or 1 – 126` | `1.0.0.0 – 126.255.255.255` | `255.0.0.0 (/8)` | Large networks |
| B | `10` | `128 – 191` | `128.0.0.0 – 191.255.255.255` | `255.255.0.0 (/16)` | Medium networks |
| C | `110` | `192 – 223` | `192.0.0.0 – 223.255.255.255` | `255.255.255.0 (/24)` | Small networks |
| D | `1110` | `224 – 239` | `224.0.0.0 – 239.255.255.255` | N/A | Multicast |
| E | `1111` | `240 – 255` | `240.0.0.0 – 255.255.255.255` | N/A | Experimental / Research |

## Network Bit is represented by 1

## Host Bit is represented by 0 

## We mostly work on private ip and with class A , B and C





