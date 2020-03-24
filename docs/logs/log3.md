# Log Entry 3
March 17, 2019  

Now that the QUIC server and client is running and able to handle requests, we decided to take a look at the packets in Wireshark. Please note that currently the members of our group are experiencing various technical difficultes that may include the number of packets being transferred for the requests to vary, or the requests returning a 404. However, here is the packet capture for a simple requestion as explained in Log Entry 3.  

![](images/packet_capture.png)

#### Observations
* As we can see, the client port is `6121` as stated in Log Entry 2, and the server defaulted to port `53925`.
* For some reason, the first packet in the sequence originated from the server, this is likely a configuration error that we will further investigate.
* The entire exchange is 10 packets.
* Wireshark capture the QUIC traffic as UDP.