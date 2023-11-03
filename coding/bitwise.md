---
description: >-
  Bit manipulation is the act of algorithmically manipulating bits or other data
  smaller than a byte.
---

# Bit Manipulation

### Bitwise Operators

A = 0011 1100 = 60\
B = 0000 1101 = 13

<table><thead><tr><th width="157">Operator</th><th>Description</th><th>Example</th></tr></thead><tbody><tr><td>&#x26;</td><td><p>AND Operator</p><p>if it exists 1 in both values.</p></td><td>(A &#x26; B) will give 12 which is 0000 1100</td></tr><tr><td>|</td><td><p>OR Operator</p><p>if it exists 1 in either operand.</p></td><td>(A | B) will give 61 which is 0011 1101</td></tr><tr><td>^</td><td><p>XOR Operator</p><p>if it is set in one operand but not both.</p></td><td>(A ^ B) will give 49 which is 0011 0001</td></tr><tr><td>~</td><td><p>NOT Operator</p><p>flip bits</p></td><td>(~A) will give -60 which is 1100 0011</td></tr><tr><td>&#x3C;&#x3C;</td><td><p>Binary Left Shift Operator.</p><p>The left operand value is moved left by the number of bits specified by the right operand.</p></td><td>(A &#x3C;&#x3C; 2) will give 240 which is 1111 0000</td></tr><tr><td>>></td><td><p>Binary Right Shift Operator.</p><p>The left operand value is moved right by the number of bits specified by the right operand.</p></td><td>(A >> 2) will give 15 which is 0000 1111</td></tr></tbody></table>

### Bitwise Problems

> Commum bitwise uses in programming

#### Find Equal or Not Using Bitwise

```python
if num1 ^ num2:
    print("Unequal")
else:
    print("Equal")
```

#### Find Odd or Even Using Bitwise

```python
if(num&1==1):  
    print("Odd")    
else:  
    print("Even")
```

#### Swap Two Numbers Using Bitwise

```python
a = a ^ b;
b = a ^ b;
a = a ^ b;
```

#### Enable Nth Bit of a Number

```python
num |= 1 << n-1
```

#### Check if the Nth Bit is Set or Unset

```python
temp = num >> (n - 1)
if temp == 1:
    print("ON")
else:
    print("OFF")
```

#### Disable the Nth Bit of a Number

```python
num |= 1 << n-1
num ^= 1 << n-1
```

#### Toggle the Nth Bit of a Number

```python
num ^= 1 << n-1
```
