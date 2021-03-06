# Networking

# Contents
* [Networks](##Networks)
* [IP Addresses](##IP-Addresses)
* [Submask and CIDR blocks](##Submask-and-CIDR-blocks)
* [OSI Model](##OSI-Model)

## Networks
* A computer network is 2 or more machines that are connected together in order to communicate.
* Can be logically partitioned into subnets.
* Networking requires a networking device such as a router or switch.    
![diagram](images/simplenetworkdiagram.png)

## IP Addresses
* Each machine on the network has a unique internet protocol (IP) address assigned to it.
* Expressed in a hexademical format.
* Machines will convert to binary format
### IPVv4 vs IPv6
#### IPv4
* IPv4 - 32 bit addresses
* 4 x 8bits --> 4 numbers, each represent 8 bits.
* Each number can be any value from 0 to 255
* Example:    
```
Hexademical -->   192   .    0    .  2    .    0
Binary      --> 11000000.00000000.00000010.00000000
```   
![ipv4](images/ipv4.png)

* IPv4 has a limit of 2<sup>32</sup> addresses which is approximately 4.3 billion addresses. This limit has already been reached therefore leading to IPv6.
#### IPv6
* IPv6 - 128 bit addresses
* Can contain non-numeric characters
* 8 x 16 bits --> 8 characters, each represent 16 bits
* 16 bits --> 0 to ffff
* Example
```
2600:1f18:22ba:8c00:ba86:205e:25ba:00FF
```

## Submask and CIDR blocks
* CIDR is a common method to describe networks and groups of IP addresses.
* Expressed as an IP Address followed by / and then a number which tells you how many bits must be steady and allocated for a network identifier.
```
192   .  0  .  2   .     0             /      24
network identifier  host identifier     no. of fixed bits
    (fixed)           (flexible)
```

* CIDR is a way to express a group of IP addresses that are consecutive to each other.
*  A CIDR block is an abbreviation of the size of a submask
```
/32 --> 255.255.255.255
/24 --> 255.255.255.0
/16 --> 255.255.0.0
/8 --> 255.0.0.0
/0 --> 0.0.0.0
```

## OSI Model
* Open Systems Interconnection Model
* Used to understand how communication takes place in the cloud and basic networking.

|     Layer    | Number |                               Function                              |    Protocol/Address   |
|:------------:|:------:|:-------------------------------------------------------------------:|:---------------------:|
|  Application |    7   | Means for an application to access a computer network               | HTTP(s),FTP,DHCP,LDPA |
| Presentation |    6   | Ensure that an app layer can read data. Encryption                  |       ASCI, ICA       |
|    Session   |    5   | Enables orderly exchange of data                                    |      NetBIOS, RPC     |
|   Transport  |    4   | Provides protocol to support host-to-host communication             |        TCP, UDP       |
|    Network   |    3   | Routing and packet forwarding (routers)                             |           IP          |
|   Data Link  |    2   | Transfer data in the same LAN network                               |          MAC          |
|   Physical   |    1   | Transmission and reception of raw bitstreams over a physical medium |        Signals        |



## VPC
* Virtual Private Cloud - A virtual network dedicated to your AWS account. Resembles a traditional network infrastructure with the benefits of rapid scalability offered by AWS.
* Subnet - Range of IP addresses in your VPC. Belong to a single of availability zone. 
* Route Table - A set of rules that are used to determine where network traffic is directed.
* Internet Gateway - Enables communication between VPC and internet.

## Bastions
* Bastion - Fortified wall/structure. Safeguards what is inside
* In computing?
* > A bastion is a special purpose server instance that is designed to be the primary access point from the Internet and acts as a proxy to your other EC2 instances.
[*source*](https://aws.amazon.com/blogs/security/controlling-network-access-to-ec2-instances-using-a-bastion-server/)
