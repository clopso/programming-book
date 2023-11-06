---
description: Introducing Bluetooth LE and its stack layers.
---

# Layers

The Bluetooth Low Energy (BLE) protocol stack is divided into **three** main components or subsystems: the application layer, the host layer, and the controller layer.

It is responsible for **managing** the state of the LE radio, advertising, scanning, and creating and overseeing links.

### Host

The Bluetooth LE host consists of the following layers:

* **Logical Link Control & Adaptation Protocol (L2CAP)**: provides data encapsulation services to the upper layers.
* **Security Manager Protocol (SMP)**: defines and provides methods for secure communication.
* **Attribute Protocol (ATT)**: allows a device to expose certain pieces of data to another device.
* **Generic Attribute Profile (GATT)**: defines the necessary sub-procedures for using the ATT layer.
* **Generic Access Profile (GAP)**: interfaces directly with the application to handle device discovery and connection-related services.

### Controller

The Bluetooth LE controller is comprised of the following layers:

* **Physical Layer (PHY)**: determines how the actual data is modulated onto the radio waves, and how it is transmitted and received.
* **Link Layer (LL)**: manages the state of the radio, defined as one of the following – standby, advertising, scanning, initiating, connection.
