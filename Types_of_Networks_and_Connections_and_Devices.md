## Exploring IP Addresses

In order to start exploring IP addresses, run the 'ip a' command in the Ubuntu VM

The output should look something like this:

![screenshot](assets/css/IP_A_SS.png)

Under enp0s1 is the inet followed by the IP address of the VM: 192.168.64.2

Another method of locating a devices IP address would be to visit the website https://whatismyipaddress.com

The outputted screen should look something like this:

![screenshot](assets/css/IP_wi_ss.png)

The sites detected IPv4 address can be seen in the image above: 173.95.44.210. This IP address is different from the one found earlier using the 'ip a' command due to the fact that each device has an internal and external IP address. The external IP address is how devices outside the LAN detect it. The internal IP address is how devices within the same network detect and send data to it. By using a VM in shared mode, the VM "hides behind" the IP address of the computer. In doing so, the VM conserves IP addresses and acts as a router allowing multiple VM's to communicate through one IP address. 

Now switch to the bridged mode of the VM and run the same 'ip a' command again

At this point when the 'ip a' command is ran the internal IP address may not appear. This is due to an ethernet connection in Bridged mode. Exit the VM and switch the "Bridged Interface" from automatic to en1.

Now the internal IP address should appear under enp0s1 like so:

![screenshot](assets/css/ipa_bridged.png)

Now to find the external IP address go back to https://whatismyipaddress.com using firefox on the VM. A common error when trying to run programs on the VM is that they will not open or function properly unless the 'sudo apt update & sudo apt upgrade' commands are ran. After this the outputted screen should look like this:

![screenshot](assets/css/wimipss.png)


This next portion reviews how computers connect to other devices at the first two layers of the OSI model (Physical and Data link)

Using the ubuntu vm, type 'sudo apt install ethtool -y' in order to install the ip link commands.

Next run the 'ip link show' command to reveal the MAC address of the device. The outputted screen should look like this:

![screenshot](assets/css/ipshowss.png)

The Mac address of the device corresponds to the NIC inside of the device. The MAC address is a unique hardware device that is like a nametag for data being sent to it. 

Next, by running the 'arp -n' and 'ip -s link' commands a user can view network activity. The 'arp -n' command reveals the IP and MAC addresses of the devices that the computer has been comunicating with. The commands should reveal a screen like this: 

![screenshot](assets/css/arp-n.png)

By running the 'sudo ethtool enp0s1' command the user can view how the device connects at the Physical layer.
The Outpputed screen should look like this:

![screenshot](assets/css/ethtool.png)

In the image one can see that Duplex is listed as "Unknown!". This is due to the fact that the VM is not able to directly communicate with the built-in hardware NIC. AI supports this claim below:

![screenshot](assets/css/ethtoolexpo.png)

This information came from the Exploring IP Addresses in Shared and Bridged Mode Activity

## Ethernet Cable Construction 

In order to better understand how ethernet cables connect devices to networks, the class constructed ethernet cables. 

First strip the outside casing of the wire to reveal the 4 twisted wires

<img width="758" height="694" alt="image" src="https://github.com/user-attachments/assets/e55f40d5-40fc-496f-8b16-5917fff2316e" />

After that untwist the wires and put them into the J-45 connector in this order: White/Orange, Orange, White/Green, Blue, White/Blue, Green, White/Brown, Brown

<img width="1355" height="728" alt="image" src="https://github.com/user-attachments/assets/cb2ca5c3-b843-4cf2-be4b-fafcbfc829b9" />

After that, crimp the wire and repeat. Then, test your results!

<video src="assets/css/ethernettest.MOV" controls width="600">
  Your browser does not support the video tag.
</video>

## TCP/OSI Networks

Next lets ping google by using the 'ping -c 3 goog.com' command. Note that if this command does not work but 'ping -c 8.8.8.8' command does then there is an issue with the devices DNS. The outputted screen should look like this:

<img width="884" height="169" alt="image" src="https://github.com/user-attachments/assets/3b7a3b5f-6e6e-43d7-89cf-56046ba860f0" />

After that lets run the 'ip link show' command to view the actice interface

<img width="884" height="169" alt="image" src="https://github.com/user-attachments/assets/380f3a44-d693-4c69-8b10-41c12320a3ac" />

**Note in this image**

The Interface Name: lo

The MAC Address: 1a:63:23:39:a4:2c

The Broadcast Address: ff:ff:ff:ff:ff:ff

Now run the 'arp -n' command to see the IP address and MAC address of the devices that the VM has communicated with:

<img width="884" height="57" alt="image" src="https://github.com/user-attachments/assets/3329e85c-d06a-4d4d-8115-7224e9ed3ee9" />

Next the 'ip -s link' command reveals the RX packets, TX packets and any errors:

<img width="884" height="276" alt="image" src="https://github.com/user-attachments/assets/ba3f430a-f1d4-49c9-bcb4-800f675ce898" />

Finally run 'sudo tcpdump -c 5' command in order to capture five live packets travelling through the interface:

<img width="884" height="77" alt="image" src="https://github.com/user-attachments/assets/20bf7087-bf35-430e-9cad-40f1b296020a" />

All devices on the same network identify under the same network interface. MAC addresses, unlike IP addresses, identify the hardware of the device so packets know where to go. ARP connects layer 2 and 3 so the computer knows where to send data physically. Live packets all have the same default gateway because they are devices on the same network with the same router. Layers 1 and two work together to physically and virtually send data across networks.

This information came from the tcp/osi network activity

## Topologies

In order to better understand the different network configurations, topologies were created:

### Star Topology

<img width="1192" height="733" alt="image" src="https://github.com/user-attachments/assets/c6c5b04f-4f22-4f86-af5f-83db06933b2b" />

### Bus Topology

<img width="1042" height="727" alt="image" src="https://github.com/user-attachments/assets/728d3421-649f-41fb-bcb2-7b4454c25985" />

### Ring Topology

<img width="1089" height="715" alt="image" src="https://github.com/user-attachments/assets/7a1345ab-6e3b-4a80-9506-4df46bb9f470" />

### Mesh Topology

<img width="853" height="563" alt="image" src="https://github.com/user-attachments/assets/466b661f-c408-4d7e-a6d7-8ccbfed6f41a" />

### Hybrid Topology

<img width="1481" height="672" alt="image" src="https://github.com/user-attachments/assets/2d2bcbfa-bfe4-49c3-a2ec-147016ed54cc" />

The easiest topology for a small buisness to set up would be a star topology as it is small and would only require one router. The most reliable topology if one connection failed would be a mesh topology as it has redundancy or more than one path for data to take if one fails. The most exspensive topology to implement would be a hybrid as it would require a lot of routers or router extensions as well as many endpoint devices. The school most likely uses a hybrid topology as it has more than one network. Physical layouts effect speed and reliability due to the fact that effective connection withins LANs depends somewhat on device proximity. 

This information came from the Topology Drawing Activity. 

## SOHO Networks

SOHO Networks are small office/home office networks. They typically are composed of only a few devices including a router and desktops. In order to better understand SOHO networks, diagrams were created:

![screenshot](assets/css/SOHODIA.png)

Notice that all the IP addresses have a starting three octects of 192.168.64.x. This is due to the fact that all the devices on this network have the same router or default gateway. 

Now to better view how these two devices are connected, grab a partner and test the IP addresses on each partners computer using the 'ip a' command in Ubuntu or 'ifconfig' in Mac terminal. Partners must be using different terminals due to the fact that both partners would have the same IP address if they are on the Ubuntu VM. The outputted screen of the 'ip a' command should look like this:

![screenshot](assets/css/ss1.png)

Next, test the connection between the two devices by running 'ping *Partners IP adress* ' 

The terminal should send and recieve packets will 0.0% package loss signaling a secure connection:

![screenshot](assets/css/ss2.png)

Next lets review the 'netstat -r' and 'arp -a' commands. 

The 'netstat -r' command corresponds to the network layer (layer 3) as it displays the devices routing table and how data is sent throughout the network. 

![screenshot](assets/css/netstat-r.png)

The 'arp -a' command corresponds to data link layer (layer 2) as it displays the devices mac address table. 

![screenshots](assets/css/arp-n.png)

Now lets activate the firewall. A firewall will better secure the device. Use the 'sudo ufw status' command to check if it is on and the 'sudo ufw enable' command if the firewall is inactive:

<img width="747" height="163" alt="image" src="https://github.com/user-attachments/assets/c13d469d-ef3a-44ff-bfea-ea3b89afad0d" />

Now lets configure a new Ubuntu that is 25.10 version for ARM64. Set the VM to bridged mode, Wi-Fi(en1 or 0), virtio-net-pci and a random MAC address. 

Check the IP address using the 'hostname -I' command:

<img width="698" height="43" alt="image" src="https://github.com/user-attachments/assets/e405e3c6-138d-4d3d-a594-65de691193f9" />

Next, ping a classmates using the 'ping' command:

<img width="698" height="256" alt="image" src="https://github.com/user-attachments/assets/b48675d3-4695-4082-8898-40a0e30950f3" />

Now install the traceroute command using 'sudo apt install inetutils-traceroute -y'

Then run the command to see how many hops it takes for data to get from the device to google.com. Run 'traceroute google.com'

<img width="698" height="507" alt="image" src="https://github.com/user-attachments/assets/51c751ba-e65d-4d13-bc74-2db232ca171d" />

The results reveal the different devices the data travelled through by listing IP addresses. Each IP address is a different device that the data travelled to. 

Now lets start a temporary web server on the ubuntu VM that shares the devices home folder.

use the 'python3 -m http.server 8080' command to start the server in the ubuntu vm

next open firefox and type in https://**IP ADDRESS**:8080

When attempting this one the classroom VM the website initially, the searched webserver on firefox was https://192.168.64.5:8080 as that was the IP address provided when the 'hostname -I' command was used. However, the web server responded with a "unsecure connection" error message and the VM terminal showed failed connections. Then a classmate noticed that when the 'python3 -m http.server 8080' command was being used that the terminal read "hosting server on 0.0.0.0". Due to this, https://0.0.0.0:8080 was searched up and firefox autocorrected the IP address to 127.0.0.1. This information was put into flint ai and it was unable to solve the issue. 

This lesson demonstartes how devices communicate through "hops". The traceroute command shows how devices use IP and MAC addresses to know where to send data. The network, data link and physical layers were all encorporated throughout this activity when data is being sent and received. Enabling firewalls better protect your network by not allowing viruses or other hack attempts into the network. The amount of hops that the data took to get to google.com was surprising. This activity shows how real world websites work when a user is trying to use the website from their personal device. The connection is established through ip addresses. If this activity were acomplished at home the amount of hops that it takes to get to google.com would change. 


This information came from the SOHO Activity
