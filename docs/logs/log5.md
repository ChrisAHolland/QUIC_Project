# Log Entry 5
Circa March 2020  

We have previously taken looks at the gQUIC source found [here](https://quiche.googlesource.com/quiche/). We recently imported the repository (which contains code for QUIC, HTTP2, SPDY, etc) and began to take a look at QUICs implementation. The codebase is written in C++. You can find our imported repository [here](https://github.com/ChrisAHolland/GQUIC).  

The codebase also contains comments which sometimes provide very interesting insight into how QUIC was implemented. For example `quic/core/quic_crypto_client_handshaker.cc` provides some insight into the design behind QUICs 0-RTT. As we can see [here](https://github.com/ChrisAHolland/GQUIC/blob/master/quic/core/quic_crypto_client_handshaker.cc#L119) we have the following insights providing some insight:   
```
// While 0-RTT handshakes could be considered to be like resumption, QUIC
// Crypto doesn't have the same notion of a resumption like TLS does.
```

We also found interesting pieces of information regarding server sessions, found [here](https://github.com/ChrisAHolland/GQUIC/blob/master/quic/quic_transport/quic_transport_server_session.cc#L207):  
```
// Don't set the ready bit if we closed the connection due to any error
 // beforehand.
```

We will continue to analyze the source code to find anything useful for our project.  

We were also treated with many "bloopers" like [this](https://github.com/ChrisAHolland/GQUIC/blob/master/quic/core/http/end_to_end_test.cc#L195):  
```
        }  // End of inner version loop.
      }    // End of priority_tag loop.
    }      // End of outer version loop.
  }        // End of congestion_control_tag loop.
```