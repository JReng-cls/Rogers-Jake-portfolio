### Project Overview

### Design and Planning

TCP is is connection oriented because it requires a logical connection to be established before the data transfer. UDP is connectionless because it sends data before confirming the connection is established. 
Nothing happens if a packet is lost while being transferred using UDP as UDP doesn't confirm with the destination device nor does it resend packets so the packet is lost. TCP would consume more overhead as it is more reliable due to its ability to check with the destination device and resend lost packets. 

### Technical Development

TCP vs. UDP

Multi Step Connection: 

TCP - Yes there is a three way handshake. This establishes a connection before the data transfer

UDP - No

Are Sequence Numbers Visible?:

TCP - Yes

UDP - No

Are Acknowledgement Numbers Visible:

TCP - Yes

UDP - No


### Testing and Evaluation 

<img width="690" height="705" alt="image" src="https://github.com/user-attachments/assets/97862c0b-016b-44c4-a7d9-f3e9263b3921" />

The layer responsible for this pinging is layer three which uses ICMP to to check for host accessibility and measure round-trip time across routers. 

Now lets send a ping to PC2 through PC1

<img width="705" height="711" alt="image" src="https://github.com/user-attachments/assets/0965ef99-657c-40f0-b651-79cfa431403f" />

The packets can be observed being sent to the switch then PC2 then back through again

Observing each packet it can be noticed that the sequence number and acknowledgement numbers both increase. The sender device sends a check to make sure the packets were received. 

Now lets turn off the port and try and ping again

<img width="961" height="711" alt="image" src="https://github.com/user-attachments/assets/bcd393c7-0fb6-46e0-8e04-7037473b0c34" />

Notice the packet loss is at 100%

Lets run 'ss -tln' and 'sudo ss -tlpn' on ubuntu

<img width="2130" height="782" alt="64EEC7A3-C94B-4077-AACC-C8744B8AD51C" src="https://github.com/user-attachments/assets/b464cdff-8b70-48cb-af49-0ef09b21cfa7" />

Now run 'ss -uln' 

<img width="2712" height="338" alt="A59C1265-D103-49B6-B3E5-CF5548B4EC7A" src="https://github.com/user-attachments/assets/a8f42503-6afb-4b48-8074-b924dd66d6a1" />

Notice the State is UNCONN which confirms earlier findings that the port is LISTENING or waiting for a connection. 

The process being used on port 22 is LISTENING meaning the port is waiting for a connection. 

Lets test this connection. Open three terminals on Ubuntu. On the first start listening for a connection by running 'nc -l 5000'. next type out a message by running 'nc 127.0.0.1 5000'

<img width="2712" height="338" alt="7920A1CB-9A60-467D-8FA4-A52D11A78B71" src="https://github.com/user-attachments/assets/3c64ea03-3276-4a72-813d-be67de17f433" />

<img width="2712" height="316" alt="E790B0B5-E7C7-43FF-BD0A-2D154E5BE1F6" src="https://github.com/user-attachments/assets/0733890b-82d7-423c-9aa2-73d80ebc8c7f" />

Now compare to UDP by running the listening command 'nc -u -l 6000' and send the traffic with 'nc -u 127.0.0.1 600'

<img width="2712" height="514" alt="55174442-1AE5-429B-A876-B898C253801A" src="https://github.com/user-attachments/assets/d81a37f2-dd0a-4d6b-a306-de4c540757a2" />


### Reflection and Analysis

