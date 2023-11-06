---
description: How Bluetooth LE device is identified
---

# Bluetooth address

Every Bluetooth LE device is identified by a unique **48-bit address**.

Bluetooth addresses are **categorized** as either public addresses or random addresses.

Random addresses can further be **classified** into static or private addresses, depending on whether they change or not.

Furthermore, private addresses **can either be** resolvable or non-resolvable.

{% hint style="info" %}
The public address assigned to a device is drawn out of the same IEEE address pool as MAC addresses (e.g. for ethernet, Wi-Fi), and therefore it is also commonly referred to as a Bluetooth MAC address.
{% endhint %}

### Public Address

A public address is a **fixed address** that is programmed into the device at the manufacturer.

It must be **registered** with the IEEE registration authority, and it’s globally unique to that device and cannot be erased.

There is a **fee** associated with obtaining this type of address.

### Random Address

A random address is much **more commonly used**, as it does not require registration with the IEEE and can be manually configured by the user.

It's **either** programmed within the device or created during runtime.

**You can either** have a static or a private address.

#### Random Static Address

A random static address can be allocated and then **fixed** throughout the lifetime of the device.

It can be altered at bootup, but **not** during runtime.

This is a low-cost alternative to a public address because you **don’t need** to register it.

#### Random Private Address

A private address can be used in **addition** to the public or random static address when a device wishes to protect its privacy.

This is an address that **changes periodically** and is used to hide the device’s identity and to deter device tracking.

> A random private address can be resolvable or non-resolvable.

* **Resolvable random private address**
  * Have a **pre-shared key** by which they can figure out the new address every time it changes.
  * The pre-shared key is the **Identity Resolving Key** (IRK) and is used both to generate and resolve the random address.
  * The random address is used by the peer to be able to resolve the **actual address** of the Bluetooth LE device, which is still either the public or the random static address.
  * The IRK allows the peer to **translate** the random private address into the device’s real Bluetooth LE address.
* **Non-resolvable Random Private Address**
  * It's only intended as a way to **prevent tracking**.
  * This type of address is **not** commonly used.
