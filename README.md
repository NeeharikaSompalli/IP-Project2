# IP-Project2
Reliable transfer to multiple clients over UDP

Stop and Wait ARQ Protocol

Both Server and Client codes were written using PYTHON 3.5.2. To run the code it is mandatory to have PYTHON 3.x installed in the system. Since some features of PYTHON 3.x are not available in previous versions of PYTHON, the program will not work as expected if not interpreted using PYTHON 3.x.

BUILD and EXECUTION:

PYTHON codes are interpreted and hence compilation is not necessary. Both the server and the client need to be started as follows.
1. Open the command prompt
2. Navigate to the directory where the server and the client programs are available

To run the server, type the following in the console:
python Server.py 7735 new_filename.txt p

for example,
python Server.py 7735 bla1.txt 0.05

To run the client, type the following in the console:
python Client.py server1_IP_Address    server2_IP_Address  server3_IP_Address 7735 filename.txt   MSS

for example,
python Client.py 10.139.239.40 152.14.142.228 152.14.142.226 7735 bla.txt 128 500


Note:

1. Both the server and the client sockets and threads closes after a successful transmission.

2. The TIMEOUT at the client is the time interval during which an ACK for a packet is not received. After the TIMEOUT the sender retransmits the packet to the intended receiver. The re-transmission time interval is fixed as 0.2 seconds which was selected based on the RTT observed during our testing. After the successful transmission of file , the complete time taken to transfer the file is displayed on the Client side.

3. Based on the probability provided as input to the server, the packet losses occur at the server. This will initiate a retransmission. As per the requirement the 'PACKET LOST SEQUENCE NUMBER = x' message is output at the server side.

