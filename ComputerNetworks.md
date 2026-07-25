# ComputerNetworks

# Common Networking Unit Conversions

## Data Rate (bps)

| Unit | Value in bps | Power of 10 |
|------|-------------:|------------:|
| 1 bps | 1 bps | 10⁰ |
| 1 Kbps | 1,000 bps | 10³ |
| 1 Mbps | 1,000,000 bps | 10⁶ |
| 1 Gbps | 1,000,000,000 bps | 10⁹ |
| 1 Tbps | 1,000,000,000,000 bps | 10¹² |
| 1 Pbps | 1,000,000,000,000,000 bps | 10¹⁵ |

> **Networking uses decimal (SI) units:**  
> 1 Kbps = **1000 bps** (not 1024 bps)

---

## Data Size (Bytes)

| Unit | Value in Bytes | Power of 2 | Power of 10 |
|------|---------------:|-----------:|------------:|
| 1 KB | 1,024 Bytes | 2¹⁰ | ≈10³ |
| 1 MB | 1,048,576 Bytes | 2²⁰ | ≈10⁶ |
| 1 GB | 1,073,741,824 Bytes | 2³⁰ | ≈10⁹ |
| 1 TB | 1,099,511,627,776 Bytes | 2⁴⁰ | ≈10¹² |

---

## Bits and Bytes

| Conversion | Value |
|------------|------:|
| 1 Byte (B) | 8 bits (b) |
| 1 KB | 1024 Bytes |
| 1 MB | 1024 KB |
| 1 GB | 1024 MB |
| 1 TB | 1024 GB |

---

# Time Unit Conversions

| Unit | Seconds | Scientific Notation |
|------|---------:|--------------------:|
| 1 second (s) | 1 s | 10⁰ s |
| 1 millisecond (ms) | 0.001 s | 10⁻³ s |
| 1 microsecond (µs) | 0.000001 s | 10⁻⁶ s |
| 1 nanosecond (ns) | 0.000000001 s | 10⁻⁹ s |
| 1 picosecond (ps) | 0.000000000001 s | 10⁻¹² s |

---

## Time Conversion Summary

| From | To |
|------|----|
| 1 s | 1000 ms |
| 1 ms | 1000 µs |
| 1 µs | 1000 ns |
| 1 ns | 1000 ps |

---

# Scientific Prefixes

| Prefix | Symbol | Power of 10 |
|--------|:------:|------------:|
| Kilo | k | 10³ |
| Mega | M | 10⁶ |
| Giga | G | 10⁹ |
| Tera | T | 10¹² |
| Peta | P | 10¹⁵ |
| Milli | m | 10⁻³ |
| Micro | µ | 10⁻⁶ |
| Nano | n | 10⁻⁹ |
| Pico | p | 10⁻¹² |

---

# Quick Exam Facts

- **1 Byte = 8 bits**
- **1 Kbps = 1000 bps**
- **1 Mbps = 1000 Kbps = 10⁶ bps**
- **1 Gbps = 1000 Mbps = 10⁹ bps**
- **1 second = 1000 ms**
- **1 ms = 1000 µs**
- **1 µs = 1000 ns**
- **1 ns = 1000 ps**
- **Storage:** 1 KB = 1024 Bytes
- **Network Speed:** 1 Kbps = 1000 bps

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


## How to identify a IP class ?

see first octet 

eg - 137.128.122.36

here 137 so it will come in class B

# In class A first octet is reserved for network and rest 3 for host 

| Octet 1 (8 bit)   | Octet 2 (8 bit)  | Octet 3 (8 bit)  | Octet 4 (8 bit) |
|:-----------:|:-----------:|:-----------:|:-----------:|
| Network       |  Host |  Host |  Host |

# In class B first two octet are reserved for network and rest 2 for host 

| Octet 1 (8 bit)   | Octet 2 (8 bit)  | Octet 3 (8 bit)  | Octet 4 (8 bit) |
|:-----------:|:-----------:|:-----------:|:-----------:|
| Network       | Network |  Host |  Host |

# In class C first three octet are reserved for network and rest 1 for host 

| Octet 1 (8 bit)   | Octet 2 (8 bit)  | Octet 3 (8 bit)  | Octet 4 (8 bit) |
|:-----------:|:-----------:|:-----------:|:-----------:|
| Network       |Network |  Network |  Host |

# Eg 1  --> 115.10.0.15 -

## Here it belongs to class A

##  here network id is 115.0.0.0

## because in In class A first octet is reserved for network and rest 3 for host 

# Eg 2 -->  196.10.10.0 -

## Here it belongs to class C

##  here network id is 196.10.10

## because In class C first three octet are reserved for network and rest 1 for host  


# Subnet Mask ?

#### Eg - Find subnet mask of -> 115.10.10.20

## Here it belongs to class A

## here network part is 115.0.0.0

## and 10.10.20 is for host part




