# Avinash-Pranav-BinaryBandits-
Welcome to the repository for our RISC-V IoT Hackathon project!
# RISC-V IoT Hackathon Project

Welcome to the repository for our RISC-V IoT Hackathon project!

## Introduction

This project was developed as part of the RISC-V IoT Hackathon. Our goal was to create an innovative IoT application using the RISC-V architecture. This project showcases the potential of RISC-V in the IoT space by leveraging its flexibility and efficiency.

## Overview

The project involves integrating various sensors with a RISC-V development board to collect and process data in real-time. The data is then transmitted to a central server for further analysis and visualization. A user-friendly interface allows users to monitor and control the system.

## Components (Bill of Materials - BOM)

- **RISC-V Development Board**: VSD Squadron Mini
- **Sensors**:
  - Temperature Sensor
  - Humidity Sensor
  - Light Sensor
- **Communication Modules**:
  - Wi-Fi Module
  - Bluetooth Module
- **Power Supply**: 5V/2A Power Adapter
- **Miscellaneous**:
  - Breadboard
  - Jumper Wires
  - Resistors
  - Capacitors

## Circuit Connection Diagram

Below is the circuit connection diagram based on the VSD Squadron Mini specification sheet.

![Circuit Diagram](link-to-circuit-diagram-image)

## Pin Connection Table

| Component           | Pin on Component | Pin on VSD Squadron Mini |
|---------------------|------------------|--------------------------|
| Temperature Sensor  | VCC              | 3.3V                     |
|                     | GND              | GND                      |
|                     | DATA             | GPIO2                    |
| Humidity Sensor     | VCC              | 3.3V                     |
|                     | GND              | GND                      |
|                     | DATA             | GPIO3                    |
| Light Sensor        | VCC              | 3.3V                     |
|                     | GND              | GND                      |
|                     | DATA             | GPIO4                    |
| Wi-Fi Module        | VCC              | 3.3V                     |
|                     | GND              | GND                      |
|                     | RX               | TX1                      |
|                     | TX               | RX1                      |
| Bluetooth Module    | VCC              | 3.3V                     |
|                     | GND              | GND                      |
|                     | RX               | TX2                      |
|                     | TX               | RX2                      |

For detailed specifications, please refer to the [VSD Squadron Mini Datasheet](https://www.vlsisystemdesign.com/docs/vsdsquadronminidatasheet/getting-started/).

## Getting Started

To get started with this project, clone the repository and follow the instructions in the `README.md` file in each component directory.

1. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/risc-v-iot-hackathon-project.git
