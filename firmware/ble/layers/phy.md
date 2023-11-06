---
description: Radio modes
---

# PHY

At the bottom of the Bluetooth LE stack is the physical layer (PHY). PHY refers to the physical layer radio specifications that **govern** the operation of the Bluetooth LE radio.

### 1M PHY

1M PHY, or 1 Megabit PHY, is the classic PHY supported by all Bluetooth LE devices. As its name implies, 1M PHY uses **1 megabit** per second.

When initiating a connection between two Bluetooth LE devices, this is the mode that **will be used**, to begin with. Then the peers can request another mode if both devices support it.

### 2M PHY

2 Megabit PHY is a new mode introduced in Bluetooth v5.0. As the name implies, it effectively doubles the data rate to **2 megabits** per second. Since the data is transmitted at a higher data rate (faster), the radio needs to stay on for less time, decreasing battery usage. The downside is the decrease in receiver sensitivity which translates to less communication range.

### Coded PHY

While 2M PHY exists for users willing to sacrifice range for increased data rate, coded PHY was introduced to serve applications where users can achieve a **longer communication range** by sacrificing data rate.

Coded PHY uses coding schemes to correct packet errors **more effectively**, which also means that a single bit is represented by more than 1 symbol.

Coded PHY uses 2 modes, S=2 and S=8. In the S=2 mode, 2 symbols represent 1 bit, therefore the data rate is **500 kbps**. While in the S=8 mode, 8 symbols are used to represent a bit and the data rate becomes 125 kbps.
