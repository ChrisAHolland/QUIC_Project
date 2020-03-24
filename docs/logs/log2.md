# Log Entry 2
March 17, 2019  

This log entry is slightly late, but details the steps we took to get toy QUIC server and client up and running on our own machines (a continuation of the steps from Log Entry 1).  

Now that we had the Chromium project installed, we could build the QUIC client and server using the following command while in `chromium/src`.  
```
ninja -C out/Default quic_server quic_client
```
The server and client took a few minutes to build, and once complete we used the following commands to create a directory to store sample data for the server to send to the client. We used the simple website [example.org](www.example.org).  
```
mkdir /tmp/quic-data
cd /tmp/quic-data
wget -p --save-headers https://www.example.org
```
Once finished, we were able to run the client and server, and request the example.org data that we downloaded! Firstly we ran the server:  
```
sudo ./out/Default/quic_server --quic_response_cache_dir=/tmp/quic-data/www.example.org --certificate_file=net/tools/quic/certs/out/leaf_cert.pem --key_file=net/tools/quic/certs/out/leaf_cert.pkcs8
```
And then we ran the server and made the request:  
```
sudo ./out/Default/quic_client --host=127.0.0.1 --port=6121 --disable_certificate_verifications https://www.example.org
```
