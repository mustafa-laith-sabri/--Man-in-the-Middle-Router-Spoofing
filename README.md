# 🛡️ Man-in-the-Middle: Router & MAC Spoofing Simulation

> A practical cybersecurity demonstration illustrating the mechanics of Man-in-the-Middle (MitM) attacks, ARP poisoning, and MAC address manipulation for network visibility and security analysis.


🔍 Overview

This project simulates a Man-in-the-Middle (MitM) attack scenario within a controlled lab environment. It demonstrates how an attacker can leverage ARP spoofing techniques, manipulate MAC addresses, and intercept network traffic to understand vulnerabilities and reinforce network defense mechanisms.
⚙️ Attack Lifecycle & Methodology

The simulation is executed through the following structured phases:

    Phase 1: Gateway Discovery

        Utilizing ARP requests to identify the default router's IP and actual MAC address.
![Interface Configuration](arp%201.png)

    Phase 2: Interface Configuration (ifconfig)
    
        Preparing and verifying the network interface on the attacker machine (Kali Linux) to be used for the operation.
![Interface Configuration](ifconfig%202.png)

    Phase 3: Network Discovery (netdiscover)

        Scanning the subnet (e.g., using CIDR notation /24) to discover all active hosts connected to the local network.
![Network Discovery](net%20dis%203.png)

    Phase 4: Target Selection

        Identifying and isolating the specific victim's IP address from the netdiscover results.
![Network Discovery](net%20dis%204.png)
![Network Discovery](target%205.png)

    Phase 5: ARP Spoofing Execution (arpspoof)

        Poisoning the ARP cache by impersonating the router to the target, and the target to the router, using the tool arpspoof.
![Network Discovery](arpspoof%206.png)

    Phase 6: Traffic Interception (The Attack)

        Routing and capturing packets flowing between the victim and the gateway.
![Network Discovery](arpspoof%207.png)

    Phase 7: Packet Forwarding & Connection Persistence

        Enabling IP forwarding (echo 1 > /proc/sys/net/ipv4/ip_forward) to ensure the victim's internet connection remains stable, preventing suspicion.
![Network Discovery](echo%208.png)

    Phase 8: MAC Address Alteration Validation

        Observing the resulting network changes on a Windows 10 target machine, where the gateway's MAC address appears altered to match the attacker's Kali interface.

![Network Discovery](win%2010%209.png)
![Network Discovery](kali%2010.png)
