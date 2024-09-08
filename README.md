Report for Q2: Real-Time Weather Monitoring System
# Objective:
The task was to design and implement a real-time weather monitoring system with multiple weather stations sending continuous weather data to a central server. The system is designed to handle high data throughput, adapt to network conditions, and employ dynamic data compression to manage the large volume of data without overwhelming the server.

Implementation:
Client-Side (Weather Station) Code:

Weather Data Fetching: Each weather station retrieves real-time weather data using the OpenWeatherMap API for the city of Guwahati. The data includes temperature, humidity, and air pressure in JSON format.

Dynamic Compression: The retrieved weather data is compressed using the zlib compression library (zlib.h) before being transmitted to the server. This compression reduces the data size to optimize network bandwidth usage.

Data Transmission: The weather station connects to the central server via TCP (socket programming) and sends the compressed weather data in real-time, simulating continuous monitoring. A delay of 10 seconds is implemented between each transmission to emulate real-time updates.

Key Functions:

fetchWeatherData(): Fetches real-time weather data using the libcurl library.
compressData(): Compresses the fetched data using zlib for efficient transmission.
Server-Side Code:

Handling Multiple Clients: The server is designed to handle multiple weather stations (clients) concurrently using multi-threading. Each client connection spawns a new thread to manage data transmission independently, ensuring that the server can handle multiple incoming streams of weather data without being overwhelmed.

Decompression: The server receives the compressed weather data from the stations and decompresses it using the zlib library. The decompressed data is then processed and displayed in the console.

TCP Connections: The server establishes TCP connections with the weather stations, ensuring reliable and ordered data transmission.

Key Functions:

decompressData(): Decompresses the received data using zlib.
handleClient(): Manages communication with each weather station by receiving, decompressing, and displaying the weather data.
Congestion Control:

Although the TCP Reno congestion control mechanism is implemented natively by the TCP protocol stack in most systems, the task description required that the weather stations adjust their data transmission rate based on network conditions. In this case, TCP Reno ensures adaptive transmission rates under varying network conditions to avoid overloading the server and prevent network congestion.
Network Adaptability:

The server simulates a constrained network environment where available bandwidth is limited. The system adapts to this by ensuring that weather stations adjust their transmission rates and compress data dynamically, helping to manage the flow of information efficiently.
Dynamic Data Compression:

The weather station compresses the data before transmission, and the server decompresses it upon receipt. The compression adapts dynamically based on the amount of data, reducing data size to maintain efficient transmission speeds without sacrificing too much processing time.
Results:
Efficient Data Handling: The system successfully handled data from multiple weather stations simultaneously without overwhelming the server. The use of multi-threading ensured that each station’s data was processed concurrently.

Compression: The dynamic data compression feature significantly reduced the data size, optimizing bandwidth usage and ensuring timely data delivery.

Network Adaptability: The system demonstrated the ability to adapt to limited network conditions by using TCP Reno for congestion control and compressing data efficiently to avoid network overload.
