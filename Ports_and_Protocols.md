### Project Overview

### Design and Planning

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



### Reflection and Analysis

