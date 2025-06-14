<h3>Binary Code</h3>
Given n binary digits, a binary code is a mapping from a set of represented elements to a subset of $2^n$ binary numbers. Here, $n = \log_{2}M$

<h3>Binary Coded Decimal (BCD) </h3>
Different weight schemes exist. Examples shown below:

| Decimal | 8421 BCD | 84-2-1 BCD | 2421 BCD |
| ------- | -------- | ---------- | -------- |
| 7       | 0111     | 1001       | 1101     |
| 2       | 0010     | 0110       | 0010     |
| 9       | 1001     | 1111       | 1111     |
| 6       | 0110     | 1010       | 1100     |
| 0       | 0000     | 0000       | 0000     |
| 3       | 0011     | 0101       | 0011     |
<h3>5043210 (Bi-quinary)</h3>

| Decimal | 05-01234 |
| ------- | -------- |
| 0       | 10-10000 |
| 1       | 10-01000 |
| 2       | 10-00100 |
| 3       | 10-00010 |
| 4       | 10-00001 |
<h3>Excess-3 (BCD +3)</h3>

| Decimal Digit | BCD (8421) | Excess-3 Code |
| ------------- | ---------- | ------------- |
| 0             | 0000       | 0011          |
| 1             | 0001       | 0100          |
| 2             | 0010       | 0101          |
| 3             | 0011       | 0110          |
<h3>Gray Code or, Reflected Binary Code</h3>
<table>
<tr>
Binary     : B3 B2 B1 B0
Gray       : G3 G2 G1 G0

Rule:
G3 = B3
G2 = B3 ⊕ B2
G1 = B2 ⊕ B1
G0 = B1 ⊕ B0

</tr>
</table><table>
  <thead>
    <tr>
      <th>Binary to Gray</th>
      <th>Gray to Binary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <pre>
Binary     : B3 B2 B1 B0
Gray       : G3 G2 G1 G0

Rule:
G3 = B3
G2 = B3 ⊕ B2
G1 = B2 ⊕ B1
G0 = B1 ⊕ B0
        </pre>
      </td>
      <td>
        <pre>
Gray       : G3 G2 G1 G0
Binary     : B3 B2 B1 B0

Rule:
B3 = G3
B2 = B3 ⊕ G2
B1 = B2 ⊕ G1
B0 = B1 ⊕ G0
        </pre>
      </td>
    </tr>
    <tr>
      <td>
        <pre>
Example:

Binary     : 1 0 1 1
               ↓ ↓ ↓ ↓
Gray       : 1 1 1 0

G3 = B3        = 1
G2 = B3 ⊕ B2   = 1 ⊕ 0 = 1
G1 = B2 ⊕ B1   = 0 ⊕ 1 = 1
G0 = B1 ⊕ B0   = 1 ⊕ 1 = 0
        </pre>
      </td>
      <td>
        <pre>
Example:

Gray       : 1 1 1 0
               ↓ ↓ ↓ ↓
Binary     : 1 0 1 1

B3 = G3        = 1
B2 = B3 ⊕ G2   = 1 ⊕ 1 = 0
B1 = B2 ⊕ G1   = 0 ⊕ 1 = 1
B0 = B1 ⊕ G0   = 1 ⊕ 0 = 1
        </pre>
      </td>
    </tr>
  </tbody>
</table>
<h3>Alphanumeric Codes</h3>

ASCII (American Standard for Information Interchange): 128 bits
EBCDIC (Extended Binary Coded Decimal Interchange): 8 bit code
Unicode (UTF-8, UTF-16, etc. ): Universal character set for all languages, emojis, symbols (140k+ characters encoded)