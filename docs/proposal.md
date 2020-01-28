# Quic: Does the Protocol Achieve its Goals.
Austin Benoit, Chris Holland  

### Problem Statement
QUIC (Quick UDP Internet Connections) is a new transport layer protocol created by Google which aims to reduce the latency of that of TCP . QUIC is built on UDP, and therefore is not as difficult to make changes to compared to TCP; since TCP is implemented in operating system kernels and middlebox firmware. Google has recently built an undersea network cable and the Google CDN (Content Delivery Network); and Chrome has been the most popular web browser for years. This means that Google has dominian over the Link, Network, and Application layers of the interent, however, not the Transport Layer. This is where QUIC comes in [1] [2].  

Over the course of this semester, we wish to analyze the QUIC protocol to determine whether it's architecture and implementation are sufficient in meeting the goals it sets out to achieve e.g. lower latency times compared to TCP. The goal will be to build a deeper understanding of the protocol, learn about how it is implemented, and discover if anything can be improved in order to better meet its business goals.  

### Previous Work
This project will build upon the work done by Henry Baxter and Liam Simmons in an earlier offering of the CSC 466 course [3]. In their project they configured virtual machines to analyze the latency of QUIC and TCP and measure analytics. We aim to use their data and discover why the QUIC protocol performs the way it does through analysis of its implementation and architecture.

### Analytical Approach

### Expected Timeline
Week of | Deliverables
---|---
Jan 27 | Project Proposal
Feb 3 | Review current Quic implementation
Feb 17 | Goal
March 2 | Goal
March 16 | Create report
March 23 | Prepare for presentation. Finalize the report

### References
1. https://www.chromium.org/quic
2. https://docs.google.com/presentation/d/15e1bLKYeN56GL1oTJSF9OZiUsI-rcxisLo9dEyDkWQs/edit#slide=id.g5b4208ab1_0_311
3. https://csc466quic.wordpress.com/