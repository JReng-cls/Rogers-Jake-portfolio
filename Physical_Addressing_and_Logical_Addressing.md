## Physical Addressing and Logical Addressing

In order to begin this activity, first understand a MAC address. Every computer has a hardware network card called a NIC. Each NIC is assigned a permanent hardware identifier when it is manufactured. This identifier is the MAC address or Media Access Control Address. Think of this address as the computers "serial number". 

In order to better understand NICs, diagrams were created:

![screenshot](assets/css/nicdia1.png)

![screenshot](assets/css/ssdia2.png)

The MAC address labeled on the images serves as a destination address for devices sending data to that device. The RJ-45 port is for ethernet cables for a direct network connection between the device and a router. The PCIe connector is needed to power the NIC as well as data transfer. The "main chip" of the NIC is needed for sending and receiving frames. 

“Why is a MAC address considered a physical address, and how does seeing a real NIC help you
understand this?”

Answer: A MAC address is printed on the NIC, it is determined at the factory when the NIC is created.

MAC addresses are 12 charecters long

example MAc address: 62:d9:a1:34:e0

The first three pairs of the MAC address represent the OUI (Organizationally Unique
Identifier) - 62:d9:a1

Summary:

MAC addresses are determined when the NIC is created and are printed on the NIC. The MAC address in the VM is virtualized therefore not able to be located by the website https://maclookup.app/. A virtual NIC still requires a MAC address for data tranference. 


| Full MAC Address | OUI    | Vendor   | Type of Vendor | Notes                           | 
|------------------|--------|----------|----------------|---------------------------------|
|F0:18:98:AA:BB:CC |F0:18:98| Apple    | Physical       | Contains doubles like AA, BB, CC|
|3C:5A:B4:11:22:33 |3C:5A:B4| Google   | Physical       | Patterns like 11, 22, 33        |
|60:45:BD:12:34:56 |60:45:BD| Microsoft| Physical       | No noticed patterns             |
|A4:BA:DB:22:33:44 |A4:BA:DB| Dell     | Physical       | Patterns like 22, 33, 44        |
|04:1A:04:55:66:77 |04:1A:04| WaveIP   | Virtual        | Patterns like 55, 66, 77        |
|00:50:56:AA:BB:CC |00:50:56| VMware   | Virtual        | Patterns like AA, BB, CC        |
|52:54:00:12:34:56 |52:54:00| Noinfo   | N/A            | No noticed patterns             |

**Notice the physical vendors have some patterns within the MAC address such as repeating numbers or letters. Virtualization vendors also need registered OUIs because if not then they could accidentally replicate real OUIs. This activity helps the user understand MAC addresses at layer 2 by explaining how they are assigned and how devices use these to send data across networks.**

<img width="500" height="23" alt="image" src="https://github.com/user-attachments/assets/266155ba-9398-4604-a144-6a79fa1f345f" />

The information in the chart above was found using the website https://maclookup.app/search/result?mac=F0:18:98:AA:BB:CC like so:

<img width="1920" height="851" alt="image" src="https://github.com/user-attachments/assets/0b38d9d6-baba-4f06-811e-602c65284500" />


Using the Ubuntu MAC address above (62.d9.a1.34.e0.a7) users can identify the different parts of the address.

The OUI is the first three pairs (62.d9.a1) while the Device Identifier is the last three pairs (34.e0.a7). The OUI represents the first 24 bits of the MAC address and identifies the vendor. The OUI connects the NIC to the manufacturer because every OUI is registered with IEEE which allows the network to recognize who produced the NIC. The OUIs must be unique or address duplication would occur and data transference would not me secure. A MAC address needs a unique second half for the same reasons. This prevents each device from having a different MAC address by creating distinct front halfs and back halfs. Otherwise these addresses would confuse switches and routers trying to send data to a certain address that has two devices linked to it. 

Revisiting the images of the NIC diagrams, notice that MAC addresses are physically printed on the NIC. VM's create its MAC address by hiding behind the address of the desktop computer. Physical and Virtual MAC addresses both have to remain unique from one another, however physical address vendors are created by the VM's manufacturer. 

This information came from the UnderstandingPhysicalAddressing assignment. 

## Dynamic vs. Static Addressing & When to Use Each

Now lets see how devices actually receive the IPv4 and IPv6 addresses

Grab a partner and one partner load onto VM1 which will be the old ubuntu and the other load onto VM2 which is the new linux ubuntu. 

Both VMs run 'ip addr show' like so

VM1:

<img width="889" height="219" alt="image" src="https://github.com/user-attachments/assets/2063a242-a2f0-4bce-9da7-5262157f5b4b" />

VM2:

<img width="625" height="200" alt="image" src="https://github.com/user-attachments/assets/be8a8e62-5dee-427b-9925-f7c29c23713f" />

Now lets view the config files on each VM

VM1:

<img width="889" height="134" alt="image" src="https://github.com/user-attachments/assets/aa2da2ae-7836-4a4b-8a39-a180b80a4823" />

VM2:

<img width="628" height="272" alt="image" src="https://github.com/user-attachments/assets/65b70b7f-62f3-42a7-b2eb-2d0cce4f1d2b" />

Now lets view which netplan file loaded by running 'ls /etc/netplan' on VM1

<img width="612" height="61" alt="image" src="https://github.com/user-attachments/assets/fea4364f-ce1b-483c-b53b-da11b97eea85" />

Dynamic addressing is when networks automatically assigns an IP address to a device when it connects to the network. Static addressing is when a user has to manually assign IP addresses. Networks should employ both for easy reliable and changable addressing. 

## Configuring and Verifying IP Addresses on a Linux VM

Start by runnong 'ip link show' on VM2 or the linux ubuntu VM like so:

<img width="893" height="111" alt="image" src="https://github.com/user-attachments/assets/0036a784-bc20-4637-93d1-8264a0bb2a1a" />

Notice the active interface: enp0s1

Now lets list the netplan by using the command 'ls /etc/netplan' like so:

<img width="893" height="42" alt="image" src="https://github.com/user-attachments/assets/b46c74b3-d510-46c6-a1de-5597309fe392" />

Notice files such as "00-installer-config.yaml" 

Now lets open the file: 

<img width="893" height="82" alt="image" src="https://github.com/user-attachments/assets/5a703929-a48a-4bc0-a045-2a46c4482ed2" />

Once in the file replace the contents with:

network:
  version: 2
  ethernets:
    enp0s1:
      dhcp4: no
      addresses:
        - 192.168.1.<your unique number>/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
            - 1.1.1.1

Now apply those changes by saving and exiting using ctrl+x then use the 'sudo netplan apply' command to add the changes

now run 'ip addr show' and 'ip route show' to confirm that the changes were made:

<img width="893" height="308" alt="image" src="https://github.com/user-attachments/assets/b46ea93f-fe66-4fd2-9834-867862e32d8f" />

You should see a line like: **default via 192.168.1.1 dev enp0s1** as shown above

Now lets test connectivity by running 'ping -c 4 8.8.8.8' like so:

<img width="893" height="598" alt="image" src="https://github.com/user-attachments/assets/369fe887-b5a1-4ef7-9d7f-1899a1221873" />

Notice that the ping does not work and ubuntu says that the host is unreachable when pinging from 192.168.1.1

That 192.168.1.1 address is the defualt gateway address added in earlier. Notice also in the screenshot that when the yaml file configurations are tried, ubuntu yields a warning that the defualt gateway is deprecated. This explains why the ping is unsuccessful. 

Refelcting on this activity notice that yaml files are extremly sensitive and errors can arise just from a single space that is out of place on your file. It is important to run 'sudo netplant try' before running 'sudo network apply' in order to confirm that your adjustments will work efficiently. 


## Reflection

This activity dives into the ins and outs of MAC addresses. It explains how each MAC address is different from the other in order to prevent data sending and receiving issues. In addition, it covers how to divide MAC addresses into two sets of three (The front half and the back half) in order to reveal OUIs and other identifiers. All of this information is printed in the form of a MAC address on the NIC card inside the device. The MAC address of the NIC is determined at the factory when it is created. 




