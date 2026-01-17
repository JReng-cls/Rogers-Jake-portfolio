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

## Hacker Diagram

In order to visualize hacker attempts on a LAN, diagrams were created. 

<img width="991" height="580" alt="image" src="https://github.com/user-attachments/assets/cc728cf5-ce19-4b84-b2d8-e7255bbac131" />

This diagram represents a MAC flooding attack in which the hacker floods one of the switches ports with thousands of MAC addresses forcing it into a "fail open" state giving the hacker access 

### Reflection Paragraph

This information reveals that to a ping a device the sender needs the destination device and needs to be on the same LAN using these commands. ARP assumes these devices are trustworthy because they are within the same LAN. Because ARP trust devices without verification it makes ARP vulnerable to spoofing. Bridged mode was required for this lab so that both VMs would be on the same LAN.

## Enterprise Physical Security Threat Analysis

In this activity, security measures were designed for a pharmaceutical research facility in order to better understand how to secure a network with high-profile information

Vulnerabilities Identified:

1. Lack of network segmentation - This enterprise has thousands of employees all doing different jobs even in different buildings. Segmenting this network using VLAN segmentation would not only reduce traffic but also help restrict access for certain employees with lower-level clearance

2. Physical Vulnerabilities - An enterpise of this status can be a target and needs to be physically secure so that a person wouldn't be able to walk on-site without many security checkpoints and clearance.

3. Insider Threats - Employees should be constantly monitered in order to prevent misuses of authorized access as well as improper actions such as more than one person through a door at one time

4. Packet Sniffing - This enterpise contains data worth a lot of money that could be targeted by hackers. This network needs to be encrypted and monitered at all times in order to prevent data leaks that could potentially cost the company thousands of dollars.

5. Network Device Access - All important devices that grant users access to the network should be behind locked doors containing company ID locks and cameras monitered 24/7. If access to these devices fell into the wrong hands then a hacker would be able to shut the entire network down and damage data along with it.

6. ARP Spoofing - This network needs to be encrypted behind a firewall or configured to only allow certain devices to communicate so that a hacker would not be able to overload a switch into a "fail open" mode.  

### Site Construction

<img width="948" height="583" alt="image" src="https://github.com/user-attachments/assets/5d4ab78a-792a-43b8-be49-a9ba2e00a1ef" />


The image above shows a diagram for the outside of the enterprise. The three buildings are sourrounded by an anti-climb fence with cameras every 50 yards to prevent blind spots. The entrance to the campus is blocked by a security booth where someone trying to enter would have to provide credentials and their reason for visiting. The cameras on the fence are monitired 24/7 by guards withing the data center. The anti-climb fence is patrolled by armed guards on the inside and outside at all times. All of these security measures ensure that no one can get on-site without the proper authorization.

### Building Security

In order to enter any of the buildings on campus one must have a badge and pass through medal detectors along with security guards. This entrance along with the rest of the buildings are monitored 24/7 by security. Alarms are triggered when motion is detected in certain areas to protect high-profile data. All devices are secured in locked racks and are behind locked one person at a time doorways. 

### Risk Justification

Physical controls that are the highest priority include proper authorization for site access, cameras are monitored 24/7 by security and all devices are on locked racks. Ensuring that no unauthroized access to the site ensures that theft is stopped before the theif can even get into a building. Monitoring cameras 24/7 ensures that security is aware of any employee negligance or breaches in security. Keeping devices locked up ensures that if hackers gain access to the server room then they are unable to plug in and access the companies network. A combination of these controls ensures proper data security. 



