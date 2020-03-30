# Log Entry 4
Circa March 2020

After the initial packet capture (explained in [log 3](log3.md)) we found more success with further configuration and trail/error. The client and server are now exchanging data properly and we can see the 1-RTT and 0-RTT happening before our very eyes. you can view the packet capture yourself from [here](https://github.com/ChrisAHolland/QUIC_Project/tree/master/docs/captures). Please not we are not 100% sure what each individual packet is.  

## Packet Analysis of Initial 1-RTT
**Packet 1**: Client `Inchoate CHLO`.  
**Packets 2-4**: Server `REJ` and sending client the `scfg` and `stk`.  
**Packet 5**: Believed to be the completion of the initial client request.  
**Packet 6**: Believed to the the completion of the server sending the client connection parameters.  
**Packet 7**: Completed `CHLO` and client request of `www.example.org`.  
**Pacets 8-17**: These packets must include the `SHLO` and the encrypted reponse. Some of the packets we are not entirely sure of.  

## Packet analysis of 0-RTT
With the cached connection parameters, the client can initiate a conenction and make a request to the server with 0-RTT.  
**Packet 21**: First packet of `CHLO`.  
**Packets 22-24**: `SHLO`.  
**Packets 25-31**: Must include completion of client request and `SHLO` along with the encrypted message from the server. Difficult to say which packets are totally which.  

