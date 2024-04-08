<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The project is a 32-bit Fibonacci linear feedback shift register with taps at (32, 30, 26, 25). The LFSR shifts bits to the right and XORs bits from the tapped registers and enters the value in the leftmost 1st bit.

The circuit has 8 inputs, 3 of which actively used:

| Input    | Setting         |
| -------- | -------         |
| 01       | Clock Select    |
| 02       | Input Value     |
| 03       | Input Select    |
| 04       | Not Used        |
| 05       | Not Used        |
| 06       | Not Used        |
| 07       | Not Used        |
| 08       | Not Used        |

The Clock Select input selects either a 50 MHz clock (0) or an externally provided or manual clock (1).

The Input Value allows a the user to manually enter a 0 or a 1 value into the leftmost register.

The Input Select allows the user to either enter the feedback value from the LFSR into the leftmost register, or to enter the Input Value selected from above.

The cicuit ha 8 outputs. They output the values of the 8 rightmost registers.

| Output   | Value in    |
| -------- | -------     |
| 01       | Register 25 |
| 02       | Register 26 |
| 03       | Register 27 |
| 04       | Register 28 |
| 05       | Register 29 |
| 06       | Register 30 |
| 07       | Register 31 |
| 08       | Register 32 |

## How to test

The circuit can be tested by powering on the circuit, and first setting the Input Select value to "1" to reset the entire LFSR to all-zeros. The Input Select value can then be switched to "0" to allow the LFSR to run. The first 100 8-bit output values of the LFSR, which may be observed using a logic analyzer should be:

[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[1 0 0 0 0 0 0 0],[0 1 0 0 0 0 0 0],
[0 0 1 0 0 0 0 0],[0 0 0 1 0 0 0 0],[0 0 0 0 1 0 0 0],[0 0 0 0 0 1 0 0],
[0 0 0 0 0 0 1 0],[0 0 0 0 0 0 0 1],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[1 0 0 0 0 0 0 0],
[1 1 0 0 0 0 0 0],[0 1 1 0 0 0 0 0],[0 0 1 1 0 0 0 0],[0 0 0 1 1 0 0 0],
[1 0 0 0 1 1 0 0],[0 1 0 0 0 1 1 0],[1 0 1 0 0 0 1 1],[0 1 0 1 0 0 0 1],
[0 0 1 0 1 0 0 0],[0 0 0 1 0 1 0 0],[0 0 0 0 1 0 1 0],[0 0 0 0 0 1 0 1],
[0 0 0 0 0 0 1 0],[0 0 0 0 0 0 0 1],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[1 0 0 0 0 0 0 0],[0 1 0 0 0 0 0 0],[1 0 1 0 0 0 0 0],[0 1 0 1 0 0 0 0],
[0 0 1 0 1 0 0 0],[0 0 0 1 0 1 0 0],[0 0 0 0 1 0 1 0],[0 0 0 0 0 1 0 1],
[0 0 0 0 0 0 1 0],[0 0 0 0 0 0 0 1],[1 0 0 0 0 0 0 0],[0 1 0 0 0 0 0 0],
[0 0 1 0 0 0 0 0],[0 0 0 1 0 0 0 0],[1 0 0 0 1 0 0 0],[0 1 0 0 0 1 0 0],
[0 0 1 0 0 0 1 0],[0 0 0 1 0 0 0 1],[0 0 0 0 1 0 0 0],[0 0 0 0 0 1 0 0],
[0 0 0 0 0 0 1 0],[0 0 0 0 0 0 0 1],[0 0 0 0 0 0 0 0],[0 0 0 0 0 0 0 0],
[0 0 0 0 0 0 0 0],[1 0 0 0 0 0 0 0]

## External hardware

No external hardware is required.
