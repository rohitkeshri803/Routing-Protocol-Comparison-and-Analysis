Project Title: Real-Time Weather Monitoring System
Overview
This project implements a real-time weather monitoring system where multiple weather stations send continuous weather data to a central server. The system is designed to handle:

High data throughput from multiple weather stations.
Adaptive data transmission using TCP Reno for congestion control.
Simulated network constraints and dynamic data compression.

Features
Efficient Data Handling: Multi-threaded server to handle data from multiple weather stations without being overwhelmed.
Congestion Control: Uses TCP Reno to dynamically adjust the data transmission rate based on network conditions.
Dynamic Data Compression: Compresses weather data before transmission and decompresses it at the server to optimize bandwidth usage.
Simulated Network Constraints: Emulates a network with limited bandwidth to test system adaptability.

File Structure
client.cpp: Client-side application (weather stations).
server.cpp: Server-side application (central weather server).
Makefile: File to compile both the weather station and server applications.

Setup and Usage
Compiling the code: Run the following command to compile the programs using the provided Makefile:
make clean
make

Running the server: On the central server machine, execute:
./server

Running the weather stations: On each weather station machine, execute:
./client


Data Transmission:
Weather stations continuously send weather data (temperature, humidity, air pressure) to the server.
The server handles incoming data, applying decompression and ensuring it does not get overwhelmed.


Implementation Details
Congestion Control (TCP Reno): Each weather station adjusts its data transmission rate based on the network conditions, ensuring optimal performance under varying bandwidth.
Dynamic Data Compression: Weather data is compressed before transmission to reduce bandwidth usage and is decompressed at the server.
Simulated Network Constraints: The server simulates a bandwidth-limited environment to test the system's ability to adapt.

Dependencies
C++ compiler (g++).
Linux environment for socket programming and TCP Reno implementation.

