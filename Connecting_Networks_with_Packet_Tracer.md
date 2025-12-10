## Connecting Networks with Packet Tracer

In this activity we will configure two different networks connected to one another and ping a device on one network from the other.

To start Drag and drop two 2911 Routers onto the page from the Network Devices section

<img width="929" height="193" alt="image" src="https://github.com/user-attachments/assets/d5802987-11f7-4dbb-b5ca-f5b33ed82e19" />

Next, click on the "End Devices" section and drag and drop one PC below both Routers. Your network should now look like this:

<img width="931" height="755" alt="image" src="https://github.com/user-attachments/assets/484af78e-34bb-48cc-9bdc-c7b905ed5d67" />

Now lets connect the devices. Click on the Connections Tab and Select the Copper Cross Over Cable

<img width="933" height="203" alt="image" src="https://github.com/user-attachments/assets/2d0240db-9534-4869-bd49-c32bb4bd0d6e" />

When the wire is selected, your cursor should then turn into what looks like a tiny Ethernet cable. Click on Router1 and select the GigabitEthernet0/1 port then click on Router2 and select the GigabitEthernet0/1 port

Your network should now lool like this:

<img width="703" height="535" alt="image" src="https://github.com/user-attachments/assets/3200c040-ed25-472c-9f9d-8be7b8c03e75" />

**Notice the red triangles on the wire, this shows that the interface is currently down**

Next Click on the Copper Straight-Through cable

<img width="953" height="192" alt="image" src="https://github.com/user-attachments/assets/21eea453-66a8-4518-a90a-83def4d1154a" />

With that Straight-Through, click on PC0 and select the FastEthernet0 port

Take the other end and click on Router 0 and connect it to the GigabitEthernet0/0 port

Use the same copper straight through cable to connect PC1 and Router1 via PC1’s FastEthernet0 port and Router1’s GigabitEthernet0/0 port

Your Network should now look like this:

<img width="823" height="547" alt="image" src="https://github.com/user-attachments/assets/664863dd-e8f2-4789-bba9-4208bf34b85f" />

Lets start configuring the network, start by clicking on Router1 and moving to the CLI tab

<img width="940" height="945" alt="image" src="https://github.com/user-attachments/assets/580ea694-6649-4703-ab14-e5234e9969fc" />

Once in the CLI tab enter these commands to configure Router1

1. **Router1> enable**

    This moves the user into Privileged EXEC mode. This gives you the ability to view configurations, save things and enter configuration mode. The user EXEC is limited to basic monitoring

2. **Router1# configure terminal**
  
    This command brings the user into Global Configuration mode where the user can make changes to the router's running configuration. This includes setting IP addresses, routes and protocols. 

3. **Router1(config)# interface g0/0**
  
    You must enter the interface context to assign IP addresses and enable the port. This interface is the port connecting Router1 to PC1

4. **Router1(config-if)# ip address 192.168.10.1 255.255.255.0**
  
    This command assigns an IP address and subnet mask to the routers G0/0 interface. This makes the router’s interface part of the 192.168.10.0/24 network. Allowing it to communicate with PC1 and act as its default gateway

5. **Router1(config-if)# no shutdown**

    This enables the interface. By default, all of the router’s interfaces are shutdown. This command brings the interface up so it can pass traffic

6. **Router1(config-if)# exit**

    Moves you back one level, from interface configuration mode to global configuration mode. **Like using ‘cd ..’ in ubuntu** 

7. **Router1(config)# interface g0/1**

    Enters interface configuration mode for GigabitEthernet 0/1

8. **Router1(config-if)# ip address 10.0.0.1 255.255.255.252**

    This assigns Router1’s G0/1 an IP in the 10.0.0.0/30 subnet. This creates a point-to-point link between Router1 and Router2. The /30 mask gives exactly two usable addresses (10.0.0.1 and 10.0.0.2), which is perfect for router-to-router links.

9. **Router1(config-if)# no shutdown**

    Enables the G0/1 interface

10. **Router1(config-if)# exit**

    Brings you from the G0/1 configuration to global configuration

11. **Router1(config)# ip route 192.168.20.0 255.255.255.0 10.0.0.2**

    This command creates a static route telling Router1 how to reach the 192.168.20.0/24 network (PC2’s LAN) via next-hop 10.0.0.2 (Router2’s G0/1). This must be done because Routers only know about directly connected networks. Static routes teach them how to reach remote networks.

12. **Router1(config)# end**

    Exits configuration mode back to privileged EXEC

13. **Router1# write memory**

    This command saves the running configuration to the startup configuration. Without this your changes would be lost if the router reboots. This makes them permanent

The finished screen should look like this:

<img width="940" height="775" alt="image" src="https://github.com/user-attachments/assets/8b162d46-4181-41a3-97e8-86e33169c12b" />

Next lets exit out of that and click on Router2. Navigate to the CLI tab and enter these commands to configure Router2

1. **Router2> enable**

    Moves you into privileged EXEC mode

2. **Router2# configure terminal**

    Enters global configuration mode

3. **Router2(config)# interface g0/0**

    Enters interface g0/0 configuration mode

4. **Router2(config-if)# ip address 192.168.20.1 255.255.255.0**

    Assigns Router2’s G0/0 an IP address and subnet mask. This makes Router2 part of PC2’s LAN and allows it to act as the default gateway for PC2

5. **Router2(config-if)# no shutdown**

    Enables the interface

6. **Router2(config-if)# exit**

    Returns to global configuration mode

7. **Router2(config)# interface g0/1**

    Enters interface g0/1 configuration mode

8. **Router2(config-if)# ip address 10.0.0.2 255.255.255.252**

    Assigns Router2’s G0/1 an IP in the 10.0.0.0/30 subnet. - This creates the point‑to‑point link between Router1 and Router2. Router1 uses 10.0.0.1, Router2 uses 10.0.0.2

9. **Router2(config-if)# no shutdown**

    Enables the G0/1 interface

10. **Router2(config-if)# exit**

    Brings you back to global configuration

11. **Router2(config)# ip route 192.168.10.0 255.255.255.0 10.0.0.1**

    Creates a static route telling Router2 how to reach the  network (PC1’s LAN) via next‑hop  (Router1’s G0/1). Routers only know about directly connected networks. This static route teaches Router2 how to reach PC1’s subnet.

12. **Router2(config)# end**

    Exits configuration mode back to privileged EXEC

13. **Router2# write memory**

    Saves the running configuration to startup configuration

The finished screen should look like this:

<img width="939" height="776" alt="image" src="https://github.com/user-attachments/assets/c106233b-c763-49b5-9b6f-c7f4d09d21b7" />

Next click on PC1 and navigat eto FastEthernet0 under Config

<img width="947" height="952" alt="image" src="https://github.com/user-attachments/assets/18f0c3e9-d113-4d91-94aa-78285d5bd2d3" />

Enter in the IPv4 Address 192.168.10.2 and the Subnet mask 255.255.255.0. This gives PC1 a unique identifier in the 192.168.10.0/24 subnet. Without this IP address, the PC cannot communicate on the network. This IP address must match the subnet of the routers so that they can communicate with each other. The 255.255.255.0 defines which portion of the IP is the network and which is the host. This ensures that PC1 knows all addresses with 192.168.10.x are local. 

Next go to the Settings tab under config and enter in the default gateway 192.168.10.1. This tells PC1 where to send traffic destined for outside its subnet. Router1’s G0/0 is the gateway to other networks. Without this, PC1 can’t reach PC2.

The Settings tab should now look like this: 

<img width="935" height="940" alt="image" src="https://github.com/user-attachments/assets/234c10bb-35f4-44b6-a85a-b6f8943dcecb" />

Next, exit out and click on PC2 and go to the same config tab

Under settings enter in the default gateway 192.168.20.1. This points PC2 to Router2’s G0/0 for traffic outside its subnet. This allows PC2 to reach PC1 through Router2 > Router1.

The settings tab should now look like this on PC2:

<img width="933" height="947" alt="image" src="https://github.com/user-attachments/assets/63378b03-931f-4351-af99-4dff12cb39a8" />

Under the FastEthernet0 tab enter in the IPv4 address 192.168.10.2 and the Subnet Mask 255.255.255.0

Congratulations you have successfully set up your network

Let’s test to see if are work is correct!

Lets try and ping PC2 from PC1. Click on PC1 and go to the command prompt

Once in the command prompt enter ‘ping 192.168.20.2’ which is PC2’s IP address

If everything was done correctly then the output should be something like this:

<img width="941" height="270" alt="image" src="https://github.com/user-attachments/assets/5e036c63-327b-429c-a158-2623c8902f00" />

Now lets setup a simple firewall on Router1’s G0/1 interface that blocks all traffic on that port

Open up Router1’s CLI

1. **Enable**

    Moves from user EXEC (Router>) into privileged EXEC (Router#)

2. **configure terminal**

    Enters global configuration

3. **access-list 100 deny ip any any**

    Creates ACL 100 with a single rule: deny all IP traffic from any source to any destination. This is the simplest possible firewall - it blocks everything.

4. **interface g0/1**

    Opens the G0/1 interface

5. **ip access-group 100 in**

    Attaches ACL 100 to traffic entering Router1’s G0/1 interface. This means any packet arriving from Router2 (including PC2’s traffic) will be blocked before Router1 can forward it to PC1.

6. **end**

    Back to privileged EXEC mode

7. **write memory**

    Saves the running config to the startup config

The finished screen should look like this:

<img width="939" height="950" alt="image" src="https://github.com/user-attachments/assets/2e60f551-411f-4986-ac3c-7e5ad5274ec5" />

Now lets try and ping PC1 from PC2

Open up PC2’s Command Prompt and enter ‘ping 192.168.10.2’ (PC1’s IP address)

<img width="940" height="953" alt="image" src="https://github.com/user-attachments/assets/07738749-61eb-44db-be91-53636958b067" />

The ping fails! Congratulations you have successfully setup a firewall

---
