---
description: How secure is Bluetooth LE
---

# Security Models

## Security concerns

There isn’t a simple answer to the question “**How secure is Bluetooth LE?**” It depends heavily on how the pairing process is executed and what I/O capabilities the peer devices have.

There are 3 common **types of attacks** that Bluetooth LE security must cope with:

* Identity tracking
* Passive eavesdropping (sniffing)
* Active eavesdropping (Man-in-the-middle, or MITM)

Identity tracking exploits the Bluetooth address to **track a device**. Protecting against such attacks requires privacy protection.

This can be done by using a resolvable private address that changes randomly, where only the bonded/trusted devices can resolve the private address. The IRK (Identity resolving key) is used to **generate and resolve** the private address.

Passive eavesdropping allows an attacker to listen to data being transmitted between devices. This can be protected by **encrypting** the communication between the peers.

The challenge here is how the peer devices generate and/or exchange the **keys to encrypt** the connection securely. This was the main drawback that made Bluetooth LE legacy pairing vulnerable and created the need for LE Secure Connections.

In an active eavesdropping (or man-in-the-middle) attack the attacker **impersonates** two legitimate devices to fool them into connecting to it. To prevent this, we need to be sure that the device we are communicating with is in fact the device we want to talk to and not an unauthenticated device.

## Security Levels&#x20;

Bluetooth LE defines 4 security levels in security mode 1:

* **Level 1:** No security (open text, meaning no authentication and no encryption)&#x20;
* **Level 2**: Encryption with unauthenticated pairing
* **Level 3**: Authenticated pairing with encryption
* **Level 4**: Authenticated LE Secure Connections pairing with encryption

Each connection starts at **security level 1** and is then upgraded to a higher security level depending on which pairing method is used.

Using Just Works will bring the connection to **security level 2**. This method does not protect against MITM attacks, since the link is just encrypted, and not authenticated.

To protect against MITM, the connection needs to be at **security level 3** or higher.

This can be achieved by using either Passkey Entry or OOB pairing method with Legacy pairing, both of which provide authentication bringing **security to level 3**.

The connection can only get **security level 4** if both peers support LE Secure Connections and either Passkey Entry, Numeric Comparison, or OOB authentication method is used.

The **Permissions** field of an attribute determines not only whether the attribute is readable and/or writeable, but also the security level required of that connection for the attribute to be accessible.

For instance, if a link is encrypted with **security level 2**, unauthenticated encryption, the peer will not be able to access any characteristic that requires a higher level of security.

This way, we can configure our attribute table so that the data **can only be exchanged** when the link is encrypted with a certain level of security.

{% hint style="info" %}
Bluetooth LE has a total of 3 security modes. Security mode 2 uses data signing for security and is rarely used. Security mode 3 pertains to isochronous broadcast which is used with Bluetooth LE Audio and is fairly new. This course only focuses on security mode 1.
{% endhint %}

## Filter Accept List

Filter Accept List, formerly known as **Whitelisting**, is a way of limiting access to a list of devices in both advertising and scanning.

When used in advertising, **only the devices** in the Filter Accept List can send a connection request to establish a connection or send a scan request to get the scan response from the advertiser. If a device not on the list sends these requests, the advertiser will ignore the request.

When used in scanning, **only** the advertising and scan response packet from the devices in the list will be scanned and reported to the application. The scanner will filter out any packet from other advertisers.

By using the peer’s address and the identity keys distributed at **phase 3** of the pairing process, we can build the Filter Accept List to only allow a bonded and authorized device to connect to the device.

You can decide if a new device can join this list or not by adding a “pairing mode” which **temporarily turns off** the Filter Accept List and can turn it back on after the pairing is finished. In exercise 2 of this chapter we will have a look at the implementation of this mechanism.
