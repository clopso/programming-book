---
description: >-
  Prior to Bluetooth v4.2, legacy pairing was the only pairing method available
  on Bluetooth LE.
---

# Legacy Pairing vs LE Secure Connections

Legacy pairing is quite simple and **presents a risk** because the short-term key (STK) used to encrypt the link can be easily cracked.

When using Just Works in Legacy pairing, the TK is set to 0, which offers **no protection** in terms of eavesdropping or Man-In-The-Middle (MITM). An attacker can easily brute force the STK and eavesdrop on the connection, and there is also no way of verifying the devices.

Using Passkey entry is a bit better, as the TK is now a **6-digit number** that is passed between the devices by the user. For example, one of the devices displays the number on its screen, and the user inputs this number on the other devices using a keyboard.

Unfortunately, an attacker can **easily sniff** the values being exchanged, and it is then very easy to figure out the STK and decrypt the connection.

Even if it isn’t able to determine the TK directly, the key can **easily be cracked** by trying all the 999999 combinations.

In Out of Band pairing, the TK is exchanged by **some other means** than Bluetooth LE, for example, by using NFC. This method supports using a TK as big as 128 bits, which increases the security of the connection.

The security of the OOB channel used during the exchange also **determines the protection** of the Bluetooth LE connection. If the OOB channel is protected from eavesdropping and MITM attacks, so is the Bluetooth LE link.

Legacy pairing is **not recommended** by the Bluetooth SIG, but if you must use it, use OOB pairing. Out-of-band authentication is the sole method that can be considered secure when pairing with legacy pairing.

## LE Secure Connections

For this reason, LE Secure Connections was **introduced in Bluetooth v4.2**. Instead of using a TK and STK, LE Secure Connections uses Elliptic-Curve Diffie-Hellman (ECDH) cryptography to generate a public-private key pair.

The devices exchange their public keys. They will use one of the **four pairing methods** (Just Works, Passkey entry, OOB, or Numeric Comparison) to verify the authenticity of the peer device and generate the LTK based on the Diffie-Hellman key and authentication data.

The Passkey entry pairing method now uses the **passkey**, along with the ECDH public key and a 128-bit arbitrary number to authenticate the connection. This means it is much more secure than described in legacy pairing.

Using OOB pairing is still a **recommended** option, as it provides protection as long as the OOB channel is secure, just like in legacy pairing.

Additionally, a new pairing method called **Numeric Comparison** was introduced with this feature.

Although it follows the same procedure as the Just Works pairing method, it **adds another step** at the end to protect against MITM attacks by having the user perform a manual check based on values displayed on both peers.

The **only data exchanged** between the peers is the public keys. The use of the ECDH public key cryptography makes it extremely difficult to crack the LTK and is a significant improvement compared to legacy pairing.

{% hint style="info" %}
Even though LE Secure Connections is supported by most devices, there are still some Bluetooth LE products that only support Legacy pairing. Therefore, it is a good idea to enable support for Legacy pairing in addition to LE Secure Connections to achieve better interoperability in your application.
{% endhint %}
