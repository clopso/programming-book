---
description: Data exchange in Bluetooth LE
---

# GATT Operations

The GATT layer defines services and characteristics, made up of **attributes**, that are stored in the GATT server.

The server can **either** send data directly to the client or the client can poll the data from the server.

But for the client to know **what to request** from the server, it needs to know what services and characteristics the GATT server offers.

The client will perform service discovery at the **beginning** of the connection, to learn about the services and characteristics of the server, before performing any operations to access them.

* **Service discovery:** The process in which a GATT client discovers the services and characteristics in an attribute table hosted by a GATT server.

### Data Access

Remember that the communication here is based on a **client-server architecture** where the server holds the data and can send it directly to the client or the client can query the data from the server.

Hence, GATT operations are classified into **client-initiated** operations and server-initiated operations.

#### Client-initiated Operations

Client-initiated operations are GATT operations where the **client requests data** from the GATT server.

The client **can request** to either read or write to an attribute and in the case of the latter, it can choose whether to receive an acknowledgment from the server.

* **Read:** If a client wishes to read a certain value stored in an attribute on a GATT server, the client sends a read request to the server.
* **Write:** If the client wishes to write a certain value to an attribute, it sends a write request and provides data that matches the same format of the target attribute.
* **Write without response:** If this operation is enabled, a client can write data to an attribute without waiting for an acknowledgment from the server.

#### Server-initialed Operations

The other category of GATT operations is server-initiated operations, where the **server sends information** directly to the client, without receiving a request first.

* **Notify:** This is used by the server to automatically push the value of a certain attribute to the client, without the client asking for it.
* **Indicate:** This will push the attribute value directly to the client, however in this case confirmation from the client is required.

Although these operations are initiated by the server, the client is required to enable them first by subscribing to the characteristic and enabling either notifications or indications.
