---
title: Hack The MAC Address
author:
  name: 0xShakhawat
  link: https://github.com/0xShakhawat
date: 2022-02-03 11:33:00 +0600
categories: [Networking, MAC Address]
tags: [hacking, basic, networking]
---

**MAC** address is stands **Media Access Control Address** It ensures that the physical address of the Computer is unique.

MAC spoofing is a technique for changing a factory-assigned Media Access Control (​MAC) address of a network interface on a networked device.

It's just like taking over someone else's identity and performing action by impersonating them.

MAC Spoofing plays a major role when it comes to network hacking. MAC spoofing helps you overtake the identity of some other device in the network and plays a major role in one of the most dangerous attacks called Man-in-the Middle.

**​Example of a MAC Address -**
**07-1B-63-4e-45-E6**

It is a permanent, physical, and unique address assigned to network interfaces by the manufacturer.

So, whether it is a wireless card or a wired ethernet card, each of these cards comes up with addresses that are unique to themselves.

As we know, an IP address is used on the internet to identify computers and communicate between the devices.

Similarly, the MAC address is used within the network to identify devices and transfer data between devices.

Thus, each piece of data or a packet that is sent within the network contains a source MAC and a destination MAC.

Therefore, this packet would flow from the source MAC to the destination MAC.

## How To Check MAC Address

### Windows System

​Run the command
`ipconfig /all`

to check the MAC address of various network cards on your Windows system.

### Linux System

​Run the command
`ifconfig`

to check the MAC address of various network cards on your Kali Linux system.

## Why changing the MAC Address?

Since this is a physical unique address to each interface, to each network device, and because it is used to identify devices, then changing it will make you anonymous on the network.

Not only that, but the MAC address is often used by filters to prevent or allow devices to connect to networks, and do specific tasks on the network.

So, being able to change your MAC address to another device's MAC address will allow you to impersonate this device and allow you to do things that you might not be able to do.

So, you'd be able to bypass filters or connect to networks that only specific device with specific MAC addresses can connect to, and you will also be able to hide your identity. Interesting, riright

### Time For Practical

You now know what a MAC address is and its related concepts.

It is time for some practical implementation and actually performing MAC spoofing.

​Get your ​**Kali​** ready, open up the terminal, and let's start...

**Steps**

Below are the steps that will help us change the MAC address,

- Disable the interface you want to change the MAC address for
- Change the MAC address
- Change the MAC address
- Enable the interface

Simple right? Now let's see how it's done.

Run the command
`ifconfig`

Check the interface you want to change the MAC for, let's say it is the interface eth0.

In the response returned by the `ifconfig` command look for the entry "ether". This will contain the corresponding MAC address.

**Remember:** Once we change the MAC address, it doesn't stay forever, once you restart the system, the original MAC automatically replaces the spoofed one.

Follow the steps and run the given commands,

1. Disable the interface: `ifconfig eth0 down`

- Here eth0 is the name of the interface we want to change the MAC for.

2. Change the MAC: `ifconfig eth0 hw ether 00:11:22:33:44:55`

- Here 'hw' stands for hardware interface and '00:11:22:33:44:55' is the fake MAC that we have given to change the MAC. The Mac address will be changed to this given random address.

3. Enable the interface: `ifconfig eth0 up`

Now simply run the command `ifconfig` and check! The MAC address will be changed...

#### Let's do it on Windows now

Changing MAC on Kali was really interesting and simple. Let's check how it can be done on Windows. For this, we will use a tool called Technitium MAC Address Changer.

It is a freeware utility to spoof the MAC address instantly.

You can download it in your windows machine from here: [https://technitium.com/tmac/](https://technitium.com/tmac/)

**Steps**

It is very simple to use, follow the steps given below,

1. Download and install [Technitium](https://technitium.com/tmac/)
2. Execute the file
3. Go to the network connections tab in Technitium
4. Select Wifi
5. Select Random MAC Address option
6. Click on Change Now.

That's it. It's done.

**Check**

Simply go to the Windows command line and run the command `ipconfig /all`.

Notice the change in the MAC address.

Later, you can go to Technitium and restore the original one again.

### Preventing MAC Spoofing

Knowing the skills is great but, it is also necessary to know how to prevent it. Let's check that out.

MAC spoofing can be a big problem on shared segment networks. However, the current generations of Ethernet switches are offering us a basis for defeating this kind of intrusion by offering us MAC locking.

### MAC Locking

It is possible to lock a MAC address to a specific physical port on the switch.

When MAC-locking locks a MAC/port combination, it prevents the MAC address from being used from any other port on the segment.

This combined with static ARP and MAC/IP filters could totally eradicate the spoofing possibilities on a shared-segment network.

Expensive, managed switches allow port locking, but the disadvantage is the overhead cost.

### Using ARP Tables

The use of the (static) ARP table in combination with the routing table could prevent most of the shared-segment spoofing possibilities.

Most operating systems by default do not check if a received IP datagram originated from a local MAC address matches the MAC addresses in the static ARP table, or if the external datagram matches the MAC address of one of the known network routers that have a valid route entry in the routing table.

Unauthorized MAC addresses are therefore exposed, and the decision to take defensive action can then take place.

### Real Life Facts

- MAC Address is not an attack that will give you access to systems, but it will play a very important role in network hacking.
- MAC Spoofing is one of the important steps in Wifi Hacking.
- Heard of something called MITM(Man-In-The-Middle) Attacks? MAC Spoofing plays a very important role there as well.
- You can change your MAC to the MAC of another system and pretend to be someone else. Thus you can sit in the middle of the network and intercept it.

#BasicHacking
#0xShakhawat

___
wanna support my work! well just buy me a coffee  

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/shakhawat)