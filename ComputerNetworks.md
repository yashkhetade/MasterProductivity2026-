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
| A | `0` | ` 0 to 127 (theoretically) or 1 – 126 (Practically)` | `1.0.0.0 – 126.255.255.255` | `255.0.0.0 (/8)` | Large networks |
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

so subnet mask for class A is 255.0.0.0

so for class B it is 255.255.0.0

class C it is 255.255.255.0


# Convert Ip to Binary or decimal write powers of 2 


````md id="lt8e4p"
# Powers of Two (2ⁿ)

| Power | Value | Common Use |
|------:|------:|------------|
| 2⁰ | 1 | Single value |
| 2¹ | 2 | Binary digits |
| 2² | 4 | 2-bit combinations |
| 2³ | 8 | 3-bit combinations |
| 2⁴ | 16 | Hexadecimal digit values |
| 2⁵ | 32 | IPv4 address bits |
| 2⁶ | 64 | Network sizes |
| 2⁷ | 128 | Highest bit in an IPv4 octet |
| 2⁸ | 256 | Values in one octet (0–255) |
| 2⁹ | 512 | Memory |
| 2¹⁰ | 1,024 | 1 KB (binary) |
| 2¹⁶ | 65,536 | Number of TCP/UDP ports |
| 2²⁰ | 1,048,576 | 1 MB (binary) |
| 2²⁴ | 16,777,216 | Class A host addresses |
| 2³⁰ | 1,073,741,824 | 1 GB (binary) |
| 2³² | 4,294,967,296 | Total IPv4 addresses |

---

# Binary Place Values (One Octet)

| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|:---:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|

Each bit position has a value equal to a power of two:

| Bit Position | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
|:------------:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Value | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| Power | 2⁷ | 2⁶ | 2⁵ | 2⁴ | 2³ | 2² | 2¹ | 2⁰ |

---

# How to Convert Decimal to Binary

## Example 1: Convert 192 to Binary

Select the place values that add up to **192**.

|128|64|32|16|8|4|2|1|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|1|1|0|0|0|0|0|0|

**192 = 128 + 64**

**Binary = `11000000`**

---

## Example 2: Convert 168 to Binary

168 = 128 + 32 + 8

|128|64|32|16|8|4|2|1|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|1|0|1|0|1|0|0|0|

**Binary = `10101000`**

---

## Example 3: Convert 10 to Binary

10 = 8 + 2

|128|64|32|16|8|4|2|1|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|0|0|0|0|1|0|1|0|

**Binary = `00001010`**

---

# Convert an IPv4 Address to Binary

Example IP:

```
192.168.10.25
```

Convert each octet separately.

| Decimal | Binary |
|---------:|:-------:|
| 192 | 11000000 |
| 168 | 10101000 |
| 10 | 00001010 |
| 25 | 00011001 |

Final binary representation:

```
11000000.10101000.00001010.00011001
```

---

# Another Example

IP Address:

```
10.0.5.255
```

| Decimal | Binary |
|---------:|:-------:|
| 10 | 00001010 |
| 0 | 00000000 |
| 5 | 00000101 |
| 255 | 11111111 |

Binary:

```
00001010.00000000.00000101.11111111
```

---

# Quick Trick

1. Start with place values:

```
128 64 32 16 8 4 2 1
```

2. From left to right:
   - If the value fits, write **1** and subtract it.
   - Otherwise, write **0**.
   - Continue until the remainder is **0**.

Example for **25**:

```
25 - 16 = 9
9 - 8 = 1
1 - 1 = 0

128 64 32 16 8 4 2 1
 0   0   0  1 1 0 0 1

Binary = 00011001
```
````

                                                
# Find Network and Broadcast ID of 150.10.20.30

it belongs to class B 
so Network id is -  150.10.0.0

and 

Broadcast ID is 

## for Broadcast ID  the host part which you made zero give them maximum value

## so Broadcast ID is  150.10.255.255

## No of usable IP address or host is 2 power 16 -2 




# Number of Usable Hosts in Classful IPv4 Addressing

## Formula

```
Usable Hosts = 2^(Host Bits) − 2
```

### Why subtract 2?

Two IP addresses in every network **cannot be assigned to hosts**:

1. **Network Address** → Identifies the network.
2. **Broadcast Address** → Sends data to all hosts in the network.

Therefore,

```
Usable Hosts = Total Addresses − 2
```

---

# Class A

- Default Mask: `/8` (`255.0.0.0`)
- Network Bits = **8**
- Host Bits = **24**

### Calculation

```
Total Addresses = 2^24
                = 16,777,216

Usable Hosts = 2^24 − 2
             = 16,777,214
```

### Example

Network:

```
10.0.0.0/8
```

| Type | Address |
|------|---------|
| Network Address | 10.0.0.0 |
| First Host | 10.0.0.1 |
| Last Host | 10.255.255.254 |
| Broadcast Address | 10.255.255.255 |

---

# Class B

- Default Mask: `/16` (`255.255.0.0`)
- Network Bits = **16**
- Host Bits = **16**

### Calculation

```
Total Addresses = 2^16
                = 65,536

Usable Hosts = 2^16 − 2
             = 65,534
```

### Example

Network:

```
172.16.0.0/16
```

| Type | Address |
|------|---------|
| Network Address | 172.16.0.0 |
| First Host | 172.16.0.1 |
| Last Host | 172.16.255.254 |
| Broadcast Address | 172.16.255.255 |

---

# Class C

- Default Mask: `/24` (`255.255.255.0`)
- Network Bits = **24**
- Host Bits = **8**

### Calculation

```
Total Addresses = 2^8
                = 256

Usable Hosts = 2^8 − 2
             = 254
```

### Example

Network:

```
192.168.1.0/24
```

| Type | Address |
|------|---------|
| Network Address | 192.168.1.0 |
| First Host | 192.168.1.1 |
| Last Host | 192.168.1.254 |
| Broadcast Address | 192.168.1.255 |

---

# Class D

- Address Range: **224.0.0.0 – 239.255.255.255**
- Purpose: **Multicast**
- **No host calculation**
- **No subnet mask**

---

# Class E

- Address Range: **240.0.0.0 – 255.255.255.255**
- Purpose: **Experimental / Research**
- **No host calculation**
- **No subnet mask**

---

# Summary Table

| Class | Default Mask | Host Bits | Formula | Usable Hosts |
|:----:|:------------:|:---------:|:-------:|-------------:|
| A | /8 | 24 | 2²⁴ − 2 | 16,777,214 |
| B | /16 | 16 | 2¹⁶ − 2 | 65,534 |
| C | /24 | 8 | 2⁸ − 2 | 254 |
| D | N/A | N/A | Not Applicable | Multicast |
| E | N/A | N/A | Not Applicable | Experimental |

---

# Exam Tip

Remember the host bits from the default subnet mask:

- **Class A** → `/8` → **24 host bits** → **2²⁴ − 2**
- **Class B** → `/16` → **16 host bits** → **2¹⁶ − 2**
- **Class C** → `/24` → **8 host bits** → **2⁸ − 2**

**Shortcut to memorize:**

```
Class A → 24 host bits → 16,777,214 hosts
Class B → 16 host bits → 65,534 hosts
Class C → 8 host bits  → 254 hosts
```


