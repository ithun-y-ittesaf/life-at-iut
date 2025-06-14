<h3>BCD Arithmetic</h3>
for BCD sum, if sum of any BCD digit>9, it is INVALID. To fix, we add 6(decimal) to it. The difference between decimal carry and BCD carry is (16-10) = 6.
![[Pasted image 20250521043310.png]]
<h3>Error Detection</h3>
Data bits can get flipped during transmission. 
<h4>Parity</h4>
Parity is a simple error detection method. It adds an extra bit, parity bit, to make the number of 1s either even (even parity), or odd for (odd parity).
<h4>Checksum</h4>
