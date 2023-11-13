---
description: >-
  Bit manipulation is the act of algorithmically manipulating bits or other data
  smaller than a byte.
---

# Bit Manipulation

## Bitwise Operators

A = 0011 1100 = 60\
B = 0000 1101 = 13

<table><thead><tr><th width="157">Operator</th><th>Description</th><th>Example</th></tr></thead><tbody><tr><td>&#x26;</td><td><p>AND Operator</p><p>if it exists 1 in both values.</p></td><td>(A &#x26; B) will give 12 which is 0000 1100</td></tr><tr><td>|</td><td><p>OR Operator</p><p>if it exists 1 in either operand.</p></td><td>(A | B) will give 61 which is 0011 1101</td></tr><tr><td>^</td><td><p>XOR Operator</p><p>if it is set in one operand but not both.</p></td><td>(A ^ B) will give 49 which is 0011 0001</td></tr><tr><td>~</td><td><p>NOT Operator</p><p>flip bits</p></td><td>(~A) will give -60 which is 1100 0011</td></tr><tr><td>&#x3C;&#x3C;</td><td><p>Binary Left Shift Operator.</p><p>The left operand value is moved left by the number of bits specified by the right operand.</p></td><td>(A &#x3C;&#x3C; 2) will give 240 which is 1111 0000</td></tr><tr><td>>></td><td><p>Binary Right Shift Operator.</p><p>The left operand value is moved right by the number of bits specified by the right operand.</p></td><td>(A >> 2) will give 15 which is 0000 1111</td></tr></tbody></table>

## Bitwise Problems

> Commum bitwise uses in programming

### Find Equal or Not Using Bitwise

```python
if num1 ^ num2:
    print("Unequal")
else:
    print("Equal")

# A = 0011 1100
# B = 0000 1101
# ^ = 0011 0001
```

### Find Odd or Even Using Bitwise

```python
if(num&1==1):
    print("Odd")
else:
    print("Even")

# Odd
#  A  = 0001
# A&1 = 1

# Even
#  B  = 1110
# B&1 = 0
```

### Swap Two Numbers Using Bitwise

```python
A = A ^ B; # A now contains the XOR of the original values of A and B
B = A ^ B; # B now contains the original value of A
A = A ^ B; # A now contains the original value of B
```

### Enable Nth Bit of a Number

```python
num |= (1 << n-1)

# "(1 << n-1)":
# shift the number 1 to the left by n-1 bits
# creating a new number with only the nth bit set to 1.

# "num |= (1 << n-1)":
# performs a bitwise OR operation between the original
# value of "num" and the number created in step 1.

# This sets the nth bit of "num" to 1 if not already set.
```

### Check if the Nth Bit is Set or Unset

```python
temp = num >> (n - 1)
# shifts the bits of "num" to the right by n-1 positions
# moving the nth bit to the least significant position. 

if temp == 1:
    print("ON")
else:
    print("OFF")
```

### Disable the Nth Bit of a Number

```python
# Set the nth bit of "num" to 1 using the bitwise OR operator.
num |= (1 << n-1)
# toggles the state of the nth bit of "num" using the bitwise XOR operator.
num ^= (1 << n-1)
```

### Toggle the Nth Bit of a Number

```python
# toggles the state of the nth bit of "num" using the bitwise XOR operator.
num ^= (1 << n-1)
```

### Flip a boolean value

```python
# flip a boolean value
num ^= 1
```
