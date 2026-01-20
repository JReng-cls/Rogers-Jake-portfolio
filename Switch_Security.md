# Switch Security


In a LAN, the easiest devices to attack are endpoint devices as these devices security measures and procedures are left to the user. In a buisness enviorment, it is the employees job to not leave a laptop opened and unattended with sensitive information available to anyone who walks by. Devices inside the network are more dangerous as they can be used to communicate with other devices within the same VLAN and potentially attack the network using its communication abilities. A typical device can view all non-privaledged information on its own VLAN. This is typically the entire VLAN as companies separate privaledge levels by VLAN. 


<img width="818" height="633" alt="image" src="https://github.com/user-attachments/assets/748e5cbd-ccf4-4548-8aca-dc713eea9021" />



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
