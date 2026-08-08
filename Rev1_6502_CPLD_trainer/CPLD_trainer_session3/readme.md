Session 3 of CPLD trainer for 6502 described in 6502.org, https://6502.org/forum/viewtopic.php?f=10&t=6974&sid=a039497ff72fcc909848eb2e2785b9ab#p90497

Speeding up the rate of multiplexing by 1000 times will create a solid 6-digit display to our eyes. So instead of slowing down the 7.37MHz clock to 7Hz, it is divided by 1024 to about 7KHz and drive the one-hot circular shift registers.

Now lets create a 6-digit hexadecimal counter counting up: First I created a 24-bit counter (Cnt16M) driven by the same 7KHz that drives the one-hot shift registers. The same outputs of the shift registers that enable one 7-seg display at a time is also used to select one of the 6 nibbles of the 24-bit counter. The selected nibble is feed to TTL logic 7448, BCD to 7-segment decoder. Output of the 7448 drives the 7-segment display. The attached animated GIF shows the 6-digit counter counting.

You may notice that hex value $A/B/C/D/E/F are not displaying correctly. This is because 7448 does not generate the correct patterns for values greater than 9. This can be fixed by using a lookup table but lookup table is such useful concept that I want to talk about it in a separate session.
