# **Network Router Switch Fabric Simulation - README**

## **Project Overview**

This project simulates a network router switch fabric with 8 input and 8 output ports. The primary focus is on analyzing the performance of four scheduling algorithms:

- **Priority Scheduling**
- **Weighted Fair Queuing (WFQ)**
- **Round Robin (RR)**
- **iSLIP**

The simulation evaluates these algorithms under three traffic patterns (Uniform, Non-uniform, and Bursty) and compares their performance using the following metrics:

- **Queue Throughput**
- **Turnaround Time**
- **Waiting Time**
- **Buffer Occupancy**
- **Packet Drop Rate**

The project is written in C++ and demonstrates the capabilities of different scheduling algorithms to manage high-throughput traffic while ensuring fairness and efficiency in packet processing.

---

## **Project Structure**

The project consists of the following files:

1. **`main.cpp`**:  
   The main simulation file containing the implementation of the four scheduling algorithms and traffic patterns. This file includes the classes and methods for handling the router switch fabric and processing the packets.
2. **`Makefile`**:  
   A `Makefile` is included to compile the project easily using the `make` command.
3. **`README.md`**:  
   This file provides an overview of the project, how to run the code, and details on the simulation.

4. **`cn_lab_04.pdf`**:  
   A detailed lab report comparing the performance of the four scheduling algorithms and analyzing the simulation results under different traffic conditions.

---

### **Compiling the Code**

To compile the project, open a terminal and navigate to the project directory. Run the following command:

```bash
make
```

This command compiles the `main.cpp` file and creates an executable named `network_sim`.

### **Running the Simulation**

Once compiled, run the simulation using the following command:

```bash
./ps
./rr
./wfq
./iSlip
```

By default, the simulation will run with 8 input/output ports, a buffer size of 64 packets, and simulate 2000 packets. You can modify the parameters directly in the `main.cpp` file to simulate different traffic patterns.

---



### **Traffic Models**

The code simulates three types of traffic patterns:

1. **Uniform Traffic**: Even distribution of packets across all ports.
2. **Non-uniform Traffic**: Some ports receive higher-priority traffic, while others receive low-priority traffic.
3. **Bursty Traffic**: Certain ports experience random bursts of traffic, simulating peak loads.

### **Performance Metrics**

The code collects and outputs the following performance metrics:

- **Queue Throughput**
- **Turnaround Time**
- **Waiting Time**
- **Buffer Occupancy**
- **Packet Drop Rate**

---

## **Modifying the Simulation**

You can modify the simulation parameters (e.g., the number of packets, buffer size, traffic type, and port weights) by adjusting the relevant variables in the `main.cpp` file:

- **Traffic Type**:

  - `TRAFFIC_TYPE = 0`: Uniform Traffic
  - `TRAFFIC_TYPE = 1`: Non-uniform Traffic
  - `TRAFFIC_TYPE = 2`: Bursty Traffic

- **Port Weights**:  
   Modify the `portWeights` vector to assign different weights to the queues in the WFQ algorithm.

---

## **Cleaning Up**

To remove the compiled files and reset the project directory, run:

```bash
make clean
```

---

## **Known Issues**

- Ensure that your system has a functional C++ compiler and the `make` utility installed.
- Adjust the simulation parameters (e.g., number of packets, buffer size) to match the performance limits of your system.

---
