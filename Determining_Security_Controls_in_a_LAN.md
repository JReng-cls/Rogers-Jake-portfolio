## Determining Security Controls in a LAN

Which device inside a LAN would be the easiest for an attacker to compromise, and why?
Does proximity equal safety? How much can a device ‘see’ inside a LAN?

Endpoint devices would be the easiest for an attacker to compromise because usually these devices become vulnerable due to user error. Proximity can mean safety but not always, in a buisness enviorment network equipment might me locked up so the closer to that the more secure it can be. However, in other network settings, most of the security measures are established on the router and applied to all devices such as a firewall or ICMP block. A device can "see" inside a LAN by running commands such as 'ipconfig' which can show the user the running configuration.

### LAN Threat Scenario Rotation

<img width="628" height="820" alt="image" src="https://github.com/user-attachments/assets/b99c8a05-9cab-42e5-a5d5-0f07f77bed5d" />

The groups most confident hypotheses was the MAC address flooding. This is due to the lack of reasons for thousands of MAC addresses to appear on one port on a switch. The scenario that was hardest to interpret was the broadcast domain scenario. However, once a group member suggested that open ports could be abused to broadcast phishing attacks on the network the scenario became easy. Talking with another pair helped us to realize the amount of possibilities that could result in each scenario. A particular pattern noticed was that all of the situations resulted in hackers taking advantage of vulnerabilities revealed by user error. 

This information came from the Card Scenario Activity

## Apropriate Security Controls/Common Vulnerabilities Within Simple LAN

In this activity, the user will observe how easy it is to collect and manipulate ARP information inside a LAN

This activity will encorporate both VM's

VM1 - Ubuntu Desktop

VM2 - Linux Server

First run 'ip addr' and 'ip route' out VM2:

<img width="889" height="340" alt="image" src="https://github.com/user-attachments/assets/809b4237-00ac-41a9-ae14-802da4b473ff" />

**Notice the Interface name: enp0s1, the IPv4 address: 192.168.1.1 and the default gateway: 192.168.1.0**

Now on VM2, start listening for ARP traffic by running 'sudo tcpdump -i enp0s1 arp' 

Then on VM1 run 'sudo arping -c 5 -I enp0s1 192.168.1.1' to arping VM2

VM2 should get replies that look like this:

<img width="889" height="823" alt="image" src="https://github.com/user-attachments/assets/c3b22995-1a0c-482a-b532-a677e702ce85" />

### Reflection Paragraph

This information reveals that to a ping a device the sender needs the destination device and needs to be on the same LAN using these commands. ARP assumes these devices are trustworthy because they are within the same LAN. Because ARP trust devices without verification it makes ARP vulnerable to spoofing. Bridged mode was required for this lab so that both VMs would be on the same LAN.
