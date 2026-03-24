

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

Now lets examine the curl command using 'curl -I http://google.com'

<img width="2814" height="572" alt="6D75DBAF-9B50-44EB-8AD5-AA3B22D67554" src="https://github.com/user-attachments/assets/e16c970d-db37-48b1-bdd5-bf4cdbf8d103" />

The protocol being used with curl are multiple but the most common are http and https. Underneath curl is the transport protocol TCP (Transmission Control Protocol)


Now lets compare with a https address

<img width="2814" height="676" alt="BE59B62B-365A-4E29-BC4C-059FE391A6FD" src="https://github.com/user-attachments/assets/184e3d72-1a9e-4eba-a56a-bc0695965264" />

Notice all the headers are now lowercase. The additional protocol involved now is HTTPS because HTTP does not provide self encryption. 

Now lets observe encryption behavior on google.com

<img width="2814" height="1612" alt="685241F9-74C5-43A2-A760-8F7E3AE2C270" src="https://github.com/user-attachments/assets/7796e8df-13a6-462f-b3b3-bed36a417ee7" />

<img width="2814" height="1612" alt="F41B5ED4-0BAD-46F8-BD9B-3EC2C090178E" src="https://github.com/user-attachments/assets/073efe3d-1179-491c-a7ff-16d7acfd860c" />

The data being exchanged before the transfer is a connection via ip addresses. This is the transport layer as it is sending data between devices via ip addresses.


investigate whether “sessions” are visible in a real system.

<img width="2814" height="738" alt="35EAC431-9FE3-4CD8-9443-1379B9848108" src="https://github.com/user-attachments/assets/606a5771-800d-4b63-bbc3-72b21c74837c" />

The connection cannot be seen as the 'ss -tn' command was not ran quick enough to catch the data transfer.

Protocol/Purpose/layer
HTTP
HTTPS
TLS
DNS
TCP


<img width="2798" height="1278" alt="8CCF6162-6B26-4008-8A42-3BB299B7D899" src="https://github.com/user-attachments/assets/55baf5b5-af91-46a0-a3db-334d8442e51e" />

The status code returned was Http/2 301. Layer 2 is responsible for translating this message. The core difference between HTTP 301 and 302 status codes is permanence and their impact on search engine optimization

<img width="2798" height="916" alt="F4F013B4-5DB7-4B29-A195-E7E518D6BD36" src="https://github.com/user-attachments/assets/b8c73716-2d4e-4dca-9ab2-c882d7644fa6" />

This is an HTTP 301 code using layer 3. 



### Reflection and Analysis

Servers do not send a new page automatically because the user has to initiate that interaction. The server instructs the client to make a new request as the client has to initiate the request and the server wants the client to have the most up to date information available. This improves web design through more efficiency, faster data transfer, and the ability for clients to load the materials they need.
