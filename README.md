#  TRACEORA
### Your Produce Travels. We Remember.

**An Affordable and Offline First IoT Solution for Secure Farm-to-Fork Traceability**

TRACEORA represents a package tracking solution based on IoT technology aimed at improving the traceability and security of agricultural products in transit and storage. With the use of environmental monitoring, motion detection, offline logging capabilities, cryptography, GSM/SMS telematics and blockchain verifications, TRACEORA aims at making shipment tracking affordable to SMEs.

> **Detect. Record. Authenticate. Trace.**

---

##  Problem Statement

**Low-Cost IoT Blockchain Nodes for Farm-to-Fork Traceability**

Supply chains for agriculture face problems including spoilage of products, rough handling, unstable network connections, and possible lack or tampering with monitoring logs. While large companies might be able to use advanced cold chain monitoring systems, availability of these systems might be restricted for small producers and exporters.

TRACEORA addresses these issues through providing a small and affordable monitoring tool that travels along with the product and keeps a verified log of its journey despite the lack of network connection.

##  Our Solution

TRACEORA is a package-mounted sensing node that runs on an STM32 microcontroller. The system regularly captures data from its sensors, detects possible damage instances, and logs them on its local memory in a timestamped manner.

In case there is mobile phone connectivity in the area, the unit sends secure summaries and critical event information to a server through a GSM module by means of SMS-based telemetry. The server verifies the received records, builds up a history of the shipment, and provides data for an interactive web dashboard. Hashes of verified record batches can then be secured on the blockchain.

Solar power harvesting along with a battery pack is meant to increase uptime and maintenance needs.

##  Key Features

- **Environmental Monitoring:** Temperature and humidity are monitored throughout the shipment process and storage.
- **Gas-Level Monitoring:** Gas sensors act as an indicator of ripening/rotting produce depending on selectivity and calibration of the sensors.
- **Shock and Flip Detection:** Accelerometer and gyroscope readings help detect shock incidents, unusual movements, and orientations.
- **Offline-First Data Logging:** Sensors' readings and events are time-stamped and logged onto a FAT32 formatted SD card.
- **Cryptographic Authentication:** Digitally signed logs can be used for authentication of the device as well as any changes in the log files.
- **GSM/SMS Telemetry:** Condensed data and events can be sent via SMS over GSM networks without the need for internet connectivity.
- **Solar Assisted Power:** Energy harvesting using solar panels and storage in rechargeable batteries helps prolong the life of the device.
- **Blockchain Based Integrity Check:** Batch hashes of the records can be anchored on the blockchain for integrity verification.
- **Interactive Dashboard:** All shipment history, sensor readings, detected events, and record integrity check is displayed on one central dashboard.
  
##  System Architecture

```
       AGRICULTURAL PRODUCE PACKAGE
                    │
                    ▼
          ┌──────────────────┐
          │   SENSOR LAYER   │
          │ Temperature      │
          │ Humidity         │
          │ Gas Indicator    │
          │ Accelerometer    │
          │ Gyroscope        │
          └────────┬─────────┘
                   ▼
          ┌──────────────────┐
          │   STM32 MCU      │
          │ Data Processing  │
          │ Event Detection  │
          │ Digital Signing  │
          └────────┬─────────┘
                   ▼
          ┌──────────────────┐
          │   SD CARD        │
          │ Offline Data Log │
          │ FAT32 Storage    │
          └────────┬─────────┘
                   │
          Network Available
                   ▼
          ┌──────────────────┐
          │   GSM / SMS      │
          │ Signed Summaries │
          └────────┬─────────┘
                   ▼
          ┌──────────────────┐
          │  CENTRAL SERVER  │
          │ Signature Checks │
          │ Database Storage │
          └────────┬─────────┘
                   ▼
          ┌──────────────────┐
          │ BLOCKCHAIN LAYER │
          │  Batch Hashes    │
          └────────┬─────────┘
                   ▼
          ┌───────────────────┐
          │ TRACEORA WEB APP  │
          │ Shipment History  │
          │ Alerts & Analytics│
          └───────────────────┘

    POWER: Solar Panel + Rechargeable Battery
```

*Architecture defines the design of the proposed system. While developing the design, each component as well as its integration will be validated.*

##  Proposed Technology Stack

| Component | Technology / Approach |
|---|---|
| Microcontroller | STM32 |
| Environmental sensing | Temperature and humidity sensor |
| Gas sensing | Gas sensor module; ethylene selectivity requires validation |
| Motion sensing | MPU6050 accelerometer and gyroscope |
| Local storage | SD card with FAT32 filesystem |
| Communication | GSM module with SMS telemetry |
| Data security | Cryptographic signatures, sequence numbers, and hash verification |
| Backend | Server-side API and PostgreSQL database (planned) |
| Blockchain | Hash anchoring for verified record batches (planned) |
| Frontend | Interactive web dashboard |
| Power system | Solar panel, charging circuitry, and rechargeable battery pack |

*The choice of the final pieces, as well as the procedures and software architecture, can change during the course of designing and testing the prototype.*
