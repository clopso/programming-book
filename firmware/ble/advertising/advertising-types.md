---
description: Different ways that a peripheral can advertise.
---

# Advertising Types

* **Connectable vs. non-connectable:** Determines whether the central can connect to the peripheral or not.
* **Scannable vs. non-scannable:** Determines if the peripheral accepts scan requests from a scanner.
* **Directed vs. undirected:** Determines whether advertisement packets are targeted to a specific scanner or not.

The type of advertisement being used **is set in** the advertisement packet.

There are **four main** advertisement types to cover in legacy advertisements, as well as a fifth one that is used in scan responses but will not be covered here.

### Scannable and Connectable

This is the **most common** type of advertising.

If a peripheral uses this type of advertising, it means that it is **both** scannable and connectable.

This **means** that the peripheral is advertising its presence and allows the central to send a scan request and will respond with a scan response (scannable) which is followed by establishing a connection (connectable).

### Directed Connectable

This type of advertisement is used for directed advertisement where the advertiser **does not** accept scan requests.

It's directed, connectable but non-scannable. This can be used in cases where the advertiser already **knows** the scanner and just wants to reconnect quickly.

A good example of this scenario is a Bluetooth mouse that has lost the connection with the PC and just wants to reconnect again. In this case, there is no need to accept scan requests and it is **faster** to send a directed advertisement packet to shorten the connection process.

### Non-connectable and Scannable

An advertiser using this type of advertisement will **only accept** scan requests, but will not allow establishing a connection with it (non-connectable).

### Non-connectable and Non-scannable

This type of advertisement **does not** accept scan requests nor does it accept establishing connections.

A typical use-case for this type of advertisement is a beacon, where the device **does not** need to switch the radio to receiver mode since they do not allow receiving any data.

