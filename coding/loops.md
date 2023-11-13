---
description: Loops are used to repeat a block of code
---

# Loops

## Reverse loops

Reverse loops are a programming technique where a loop is written to iterate in reverse order.

### Reverse "for" loop

```c
for (int i = n; i > 0; --i) {
    // use i
}
```

### Reverse "while" loop

```c
int i = n;
while(i--) {
    // use i
}
```

### Verify all colons of a MAC address

```c
for (size_t i = 2; i < len; i += 3) {
	if (str[i] != ':') {
		return error;
	}
}
```
