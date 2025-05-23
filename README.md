# MAC-Address-and-ARP(Address-Resolution-Protocol)
### Definition:
A MAC Address is a unique hardware identifier assigned to the Network Interface Card (NIC) of a device. It is used for communication on a local network (LAN).

### Format:
48-bit (6 bytes) address, typically shown in hexadecimal.

#### Example: 00:1A:2B:3C:4D:5E or 00-1A-2B-3C-4D-5E

### Structure:
First 3 bytes: OUI (Organizationally Unique Identifier) – identifies the manufacturer.

Last 3 bytes: NIC-specific – unique to the device.

![MAC-Address](https://tse3.mm.bing.net/th?id=OIP.cLO12A8FSfN27sqLNP7n7QHaEK&pid=Api&P=0&h=220)

### Characteristics:
Burned into the hardware (ROM) of the NIC.

Uniquely identifies a device on a LAN.

Operates at Layer 2 (Data Link Layer) of the OSI model.

Doesn't change unless manually modified or spoofed.

### Types of MAC Addresses:
Unicast – Sent to one device.

Broadcast – Sent to all devices on a LAN (FF:FF:FF:FF:FF:FF).

Multicast – Sent to a group of devices.

### Uses:
Identifying devices within a LAN.

Frame delivery between devices in the same network segment.

Used by Ethernet, Wi-Fi, Bluetooth, etc.

## 2. ARP (Address Resolution Protocol)
### Definition:
ARP is a network protocol used to map an IP address to a MAC address. It ensures that devices can communicate within a local network.

### Purpose:
When a device wants to send data to another device in the same network, it needs the MAC address of the destination. ARP helps find that MAC address using the known IP address.

### How ARP Works:
A device wants to send a packet to IP 192.168.1.5, but doesn’t know the MAC address.

It sends an ARP Request (broadcast):
"Who has IP 192.168.1.5? Tell me!"

The device with that IP replies with an ARP Reply (unicast):
"192.168.1.5 is at 00:1A:2B:3C:4D:5E"

The sender stores this mapping in the ARP cache.

### Types of ARP:
Request – Broadcast asking for MAC address.

Reply – Unicast with the requested MAC address.

Gratuitous ARP – A device sends an ARP announcement to update other devices’ ARP tables.

Proxy ARP – A router answers ARP requests on behalf of another device.

### Security Risks:
ARP Spoofing/Poisoning: An attacker sends fake ARP messages to associate their MAC with the IP of a legitimate device, enabling MITM (Man-In-The-Middle) attacks.

## ARP Cache
A table stored in each device’s memory.

Maps IP addresses to MAC addresses.

Speeds up communication by avoiding repeated ARP lookups.

Entries time out or can be manually flushed.
