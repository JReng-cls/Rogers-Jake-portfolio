# Switch Security


In a LAN, the easiest devices to attack are endpoint devices as these devices security measures and procedures are left to the user. In a buisness enviorment, it is the employees job to not leave a laptop opened and unattended with sensitive information available to anyone who walks by. Devices inside the network are more dangerous as they can be used to communicate with other devices within the same VLAN and potentially attack the network using its communication abilities. A typical device can view all non-privaledged information on its own VLAN. This is typically the entire VLAN as companies separate privaledge levels by VLAN. 


<img width="818" height="633" alt="image" src="https://github.com/user-attachments/assets/748e5cbd-ccf4-4548-8aca-dc713eea9021" />

### Ubuntu Evidence Collection

To better understand how computers discover IP addresses and default gateways on their networks, tests were ran on ubuntu.

First to establish the computers default gateway the 'ip route show' command was ran

![31E2FFB2-B8CB-4E32-AE5E-EE415CBFFDEC_4_5005_c](https://github.com/user-attachments/assets/dbe4b601-8c60-4d33-85b6-96c98b51516b)

**Default Gateway Circled in Black**

Next the 'traceroute 8.8.8.8' command was ran. Tracing the route from a wireless endpoint device will reveal the default gateway on the first hop. The IP address 8.8.8.8 is for Google which is not within the computers network so the computer must go through the default gateway to access the google servers.

![DE96D8C3-F075-44E5-87AF-90070994314B_1_201_a](https://github.com/user-attachments/assets/13dca1d5-303b-45c9-931f-a18e5be5fa63)

**Default gateway circled (first hop on traceroute)**

An attacker could misuse this information if the router has no security measures in place. If the hacker knows the IP address of the default gateway then they could simply type that IP into a web browser and change network configurations. 

#### Reflection

The threat that felt most realistic would be a phishing attack as many users are not well versed in network attacks and could easily click on a link unaware to the consequences. 

### Switch Security Controls — From Observations to Decisions

Threat - Something or someone that could potentially attack the network

Vulnerability - A weak point in the network that hackers can use

Control - A security measure put in place to mitigate threats

Prevent vs. Mitigate - Prevent means to stop from happening all together while to mitigate is to lower the chance of something happening

#### Packet Tracer 

<img width="597" height="436" alt="image" src="https://github.com/user-attachments/assets/898375ab-2c55-4276-a7eb-d62eaa61b05a" />

By default this network allows any device to communicate with any other device on the network as the switch has no controls currently in place. This design assumes trust between devices because they were plugged in physically to the switch. This creates a security risk because a low level employee can view high profile information with this current configuration. 

<img width="1051" height="1063" alt="image" src="https://github.com/user-attachments/assets/2aaf1ead-adcf-4694-8967-b34687f44f27" />

The first control added to this network was VLAN segmentation. As shown in the image above, VLANs 10 and 20 were created for student and servers. VLANs change what devices can see by filtering traffic to stay within the VLAN. VLANs alone do not enforce full security as hackers can still enter high level VLANs with hacking methods such as ARP spamming or a phishing attack. 
### Mini-Threat Simulation

Scenario B— 
The Compromised Teacher  Laptop
A teacher’s laptop is infected  with malware after opening a  phishing email while  
connected to the school  
network.

The attacker only needs one piece of information: the teacher's email address.

The device that is most directly targeted is the laptop itself (endpoint device). This is due to the fact that although malware could attack any device on the network, it must go through the laptop to access the network. 

The everyday user would most likely not notice the malware as the purpose of malware is to gain information undetected by the network. 

Their would be no difference in attacker perspective between the Ubuntu VM and the Linux VM as they both simulate networks and desktops with emailing capabilities. The ability to send and receive emails is imperative to a phishing attack as the attack begins with someone clicking on a link through email. 

<img width="613" height="264" alt="image" src="https://github.com/user-attachments/assets/01516c07-b4f9-4eff-823d-3e7110e44f0c" />

**^LAN Re-design^**

Students > Teachers: Restricted - Students can't be trusted with full access to the teacher VLAN. Students need to be able to communicate with teacher devices however shouldn't nor need to have full access to the teacher VLAN

Students > Servers: Denied - Students have no need to communicate with server devices

Students > Admin: Denied - Students have no need to communicate with admin devices

Teachers > Servers: Denied - Teachers do not need to communicate with server devices

Admin > Servers: Allowed - Admin need to be able to change or configure the school network in the event of an attack or a device fails

The VLANs that should be considered the least trusted is the student VLAN. Students do not need to send anything back to the devices they only need to receieve updates and instructions. The VLAN that requires the most protection would be the server devices as they present direct access to every part of the network. The switch should be most stict on open ports so that attackers aren't able to use them without having to go through security measures. 

VLANs alone do not fully secure my design because if the attacker is able to gain access to the server VLAN then they would have access to the whole network as there are no restrictions on server communication. DHCP snooping is necessary in addition to VLANS as unused ports can still be access so network activity must be monitored. DAI is also needed to mitigate attacks as the network still allows communication on certain VLANs so an attacker could send rapid ARP messages on these VLANs. ACLs are imperative to mitigate the risk of attackers using unused ports on the switch. 

VLAN segmentation and DHCP snooping must be used together to mitigate internal risks due to the fact that DHCP snooping can see when denied VLANs are being accessed and alert the network admin. DAI depends on DHCP snooping in order to validate packets and addresses with the DHCP database. ACLs are still required even after VLAN segmentation due to fact that VLAN segmentation does not fully prevent unauthorized access. 

The hardest threat for a network admin to detect would be an email phishing attack that infects the network with malware. If the email is sent to a low level employee who in unaware of phishing attacks they might click on a link and never report it. Malware is specifically designed to go undectected in a network to collect as much information as possible, so once inside it would take a while to notice if noticed at all.
