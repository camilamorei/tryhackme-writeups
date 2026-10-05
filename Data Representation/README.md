# Data Representation

TryHackMe room: Data Representation

## Introduction

This room explains how computers represent numbers and colors using different numerical systems. It introduces binary, decimal, hexadecimal, and octal representations, as well as how RGB colors are stored in computer memory.

## Task 1 - Introduction

Computers fundamentally work with two states, represented as `0` and `1`. These states are used to represent and process different types of information.

The main topics covered in the room are:

* Binary numbers
* Hexadecimal numbers
* Octal numbers
* Color representation
* Bits and bytes

## Task 2 - Representing Colors

### RGB Colors

Computer colors can be represented using three color channels:

* Red
* Green
* Blue

When each channel has only two possible states, on or off, there are:

```text
2 × 2 × 2 = 8
```

possible colors.

Each channel can be represented by one bit:

```text
000 = Black
001 = Blue
010 = Green
011 = Cyan
100 = Red
101 = Magenta
110 = Yellow
111 = White
```

### 24-bit Colors

To represent more colors, each RGB channel can use 8 bits.

An 8-bit value can represent:

```text
2^8 = 256
```

different values.

Since there are three RGB channels:

```text
256 × 256 × 256 = 16,777,216
```

This gives more than 16 million possible colors.

A color therefore uses:

```text
3 × 8 = 24 bits
```

or:

```text
3 bytes
```

### Hexadecimal Colors

Hexadecimal makes RGB colors easier to read and write.

Every 4 bits can be represented by one hexadecimal digit.

For example:

```text
1010 = A
0011 = 3
1110 = E
1010 = A
0010 = 2
1010 = A
```

Therefore:

```text
10100011 11101010 00101010
```

can be represented as:

```text
A3EA2A
```

A hexadecimal color normally follows the `#RRGGBB` format:

```text
#RR GG BB
```

where each pair represents the intensity of red, green, and blue.

## Task 3 - Numbers

### Decimal

Decimal is the base-10 system used in everyday life.

It uses the digits:

```text
0-9
```

For example:

```text
213 = 2 × 10² + 1 × 10¹ + 3 × 10⁰
```

### Binary

Binary is the base-2 system.

It only uses:

```text
0 and 1
```

Each position represents a power of 2.

For example:

```text
1001 = 1 × 2³ + 0 × 2² + 0 × 2¹ + 1 × 2⁰
     = 8 + 0 + 0 + 1
     = 9
```

Some useful binary values are:

```text
0000 = 0
0001 = 1
0010 = 2
0011 = 3
1100 = 12
1101 = 13
1110 = 14
1111 = 15
```

### Hexadecimal

Hexadecimal is the base-16 system.

It uses:

```text
0-9
A-F
```

The letters represent values from 10 to 15:

```text
A = 10
B = 11
C = 12
D = 13
E = 14
F = 15
```

Each hexadecimal digit represents exactly 4 bits.

| Decimal | Hex | Binary |
| ------: | :-: | :----: |
|       0 |  0  |  0000  |
|       1 |  1  |  0001  |
|       2 |  2  |  0010  |
|       3 |  3  |  0011  |
|       4 |  4  |  0100  |
|       5 |  5  |  0101  |
|       6 |  6  |  0110  |
|       7 |  7  |  0111  |
|       8 |  8  |  1000  |
|       9 |  9  |  1001  |
|      10 |  A  |  1010  |
|      11 |  B  |  1011  |
|      12 |  C  |  1100  |
|      13 |  D  |  1101  |
|      14 |  E  |  1110  |
|      15 |  F  |  1111  |

For example:

```text
FF = 11111111
```

And:

```text
AB = 10 × 16 + 11
AB = 171
```

### Octal

Octal is the base-8 system.

It uses the digits:

```text
0-7
```

Every 3 binary bits can be represented by one octal digit.

For example:

```text
357 = 3 × 8² + 5 × 8¹ + 7 × 8⁰
    = 192 + 40 + 7
    = 239
```

## Key Concepts

### Bit

A bit is a binary digit that can contain either:

```text
0
```

or:

```text
1
```

### Byte

A byte consists of 8 bits.

```text
1 byte = 8 bits
```

A byte can represent 256 different values:

```text
2^8 = 256
```

### Color Representation

Using 8 bits for each RGB channel gives:

```text
256 × 256 × 256 = 16,777,216
```

possible colors.

This means a standard RGB color can be represented using 24 bits, or 3 bytes.

## Conclusion

This room introduced the basic numerical systems used in computing and showed how computers represent values using binary states.

The most important concepts were binary and hexadecimal representation, bits and bytes, and the relationship between RGB colors and hexadecimal color codes.

Understanding these representations is important in cybersecurity because binary and hexadecimal values are frequently encountered when working with tools, memory, network data, files, and other low-level computer information.

