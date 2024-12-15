42-net-practice

🪧 Overview
🌐 **NetPractice** is a practical exercise designed to help you explore and understand networking concepts. This project provides hands-on experience in configuring IP addresses, subnet masks, and related network components.

📷 Preview
![preview](imgs/preview.png)

🕹️ Usage
1. **Levels**: There are 10 levels available for training.
2. **Verify Configuration**: Complete the empty fields and click on the button `Check again` to verify if your configuration is correct.
3. **Download Configuration**: Once the exercise is successful, click on the `Get my config` button to download your configuration.
4. **Next Level**: After successfully completing a level, click on the `Next level` button to move to the next one.
5. **Start Training**: Click [here](https://ricardoreves.github.io/42-net-practice/) to begin your networking training.

🧠 Networking Basics

### What is IP?
IP (Internet Protocol) is a connectionless protocol that operates at the network layer of the OSI model. It facilitates communication between hosts by transmitting data in packets. Each device on a network is assigned an IP address, which is used to ensure data reaches its intended destination, similar to how a postal address ensures a letter reaches the correct house.

An **IP address** (for IPv4) is a 32-bit number represented in four octets, where each octet is 8 bits (1 byte). This structure can be divided into:
- **Network**: Identifies the network the IP address belongs to (e.g., street name).
- **Host**: Identifies the specific device within the network (e.g., house number).

![](https://www.packetcoders.io/content/images/2019/05/image2-1.png)

### What is Subnet Mask?
A **subnet mask** is a 32-bit number that divides an IP address into the network and host portions. This is done by setting the network bits to 1 and the host bits to 0. Subnet masks are crucial in determining how many hosts and networks can be created within a given address space.

The subnet mask also defines two special addresses:
- **Network Address**: The lowest address, used to identify the network.
- **Broadcast Address**: The highest address, used to communicate with all devices in the network.
These addresses cannot be assigned to individual hosts.

![](https://www.packetcoders.io/content/images/2019/05/image1-4.png)

### Subnet Mask Chart
Here’s a reference table to assist with subnetting. This shows the available subnets and host ranges for common subnet masks.

| Subnet Mask        | CIDR  | Binary Notation                     | Network Bits | Host Bits | Available Addresses |
|--------------------|-------|--------------------------------------|--------------|-----------|---------------------|
| 255.255.255.255    | /32   | 11111111.11111111.11111111.11111111 | 32           | 0         | 1                   |
| 255.255.255.254    | /31   | 11111111.11111111.11111111.11111110 | 31           | 1         | 2                   |
| 255.255.255.252    | /30   | 11111111.11111111.11111111.11111100 | 30           | 2         | 4                   |
| 255.255.255.248    | /29   | 11111111.11111111.11111111.11111000 | 29           | 3         | 8                   |
| 255.255.255.240    | /28   | 11111111.11111111.11111111.11110000 | 28           | 4         | 16                  |
| 255.255.255.224    | /27   | 11111111.11111111.11111111.11100000 | 27           | 5         | 32                  |
| 255.255.255.192    | /26   | 11111111.11111111.11111111.11000000 | 26           | 6         | 64                  |
| 255.255.255.128    | /25   | 11111111.11111111.11111111.10000000 | 25           | 7         | 128                 |
| 255.255.255.0      | /24   | 11111111.11111111.11111111.00000000 | 24           | 8         | 256                 |
| 255.255.254.0      | /23   | 11111111.11111111.11111110.00000000 | 23           | 9         | 512                 |
| 255.255.252.0      | /22   | 11111111.11111111.11111100.00000000 | 22           | 10        | 1024                |
| 255.255.248.0      | /21   | 11111111.11111111.11111000.00000000 | 21           | 11        | 2048                |
| 255.255.240.0      | /20   | 11111111.11111111.11110000.00000000 | 20           | 12        | 4096                |
| 255.255.224.0      | /19   | 11111111.11111111.11100000.00000000 | 19           | 13        | 8192                |
| 255.255.192.0      | /18   | 11111111.11111111.11000000.00000000 | 18           | 14        | 16384               |
| 255.255.128.0      | /17   | 11111111.11111111.10000000.00000000 | 17           | 15        | 32768               |
| 255.255.0.0        | /16   | 11111111.11111111.00000000.00000000 | 16           | 16        | 65536               |
| 255.254.0.0        | /15   | 11111111.11111110.00000000.00000000 | 15           | 17        | 131072              |
| 255.252.0.0        | /14   | 11111111.11111100.00000000.00000000 | 14           | 18        | 262144              |
| 255.248.0.0        | /13   | 11111111.11111000.00000000.00000000 | 13           | 19        | 524288              |
| 255.240.0.0        | /12   | 11111111.11110000.00000000.00000000 | 12           | 20        | 1048576             |
| 255.224.0.0        | /11   | 11111111.11100000.00000000.00000000 | 11           | 21        | 2097152             |
| 255.192.0.0        | /10   | 11111111.11000000.00000000.00000000 | 10           | 22        | 4194304             |
| 255.128.0.0        | /9    | 11111111.10000000.00000000.00000000 | 9            | 23        | 8388608             |
| 255.0.0.0          | /8    | 11111111.00000000.00000000.00000000 | 8            | 24        | 16777216            |

### Example Calculation
```
Address:   192.168.0.1           11000000.10101000.00000000 .00000001
Netmask:   255.255.255.0 = 24    11111111.11111111.11111111 .00000000
Wildcard:  0.0.0.255             00000000.00000000.00000000 .11111111
=>
Network:   192.168.0.0/24        11000000.10101000.00000000 .00000000 (Class C)
Broadcast: 192.168.0.255         11000000.10101000.00000000 .11111111
HostMin:   192.168.0.1           11000000.10101000.00000000 .00000001
HostMax:   192.168.0.254         11000000.10101000.00000000 .11111110
Hosts/Net: 254                   (Private Internet)
```

🧰 Tools
- [IP Calculator](https://jodies.de/ipcalc) – Calculate network details, including broadcast, network, and wildcard masks, as well as host ranges.

📚 References
- [techtarget.com](https://www.techtarget.com/searchnetworking/tip/IP-addressing-and-subnetting-Calculate-a-subnet-mask-using-the-hosts-formula) – How to calculate a subnet mask from hosts and subnets.
- [softwaretestinghelp.com](https://www.softwaretestinghelp.com/subnet-mask-and-network-classes/) – Guide to Subnet Mask (Subnetting) & IP Subnet Calculator.
- [avinetworks.com](https://avinetworks.com/glossary/subnet-mask/) – Glossary of Subnet Mask.
- [packetcoders.io](https://www.packetcoders.io/a-beginners-guide-to-subnetting/) – A Beginner’s Guide to Subnetting.

📝 License
Distributed under the MIT License. See [LICENSE](LICENSE) for more information.
