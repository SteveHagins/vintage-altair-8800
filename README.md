# vintage-altair-8800

This program creates a Cylon-style scanning effect on your Altair 8800's front panel data LEDs!
How it works:

A single LED sweeps from right to left (D0→D7), then back from left to right (D7→D0)
Uses the RLC (Rotate Left) and RRC (Rotate Right) instructions to shift the lit LED position
Outputs to port FFH which controls the data LEDs on the front panel
Includes a delay loop to make the sweep visible (not too fast)

To enter the program:

Set the address switches to 0000
Flip up DEPOSIT NEXT and enter each byte shown in the deposit sequence at the bottom
After entering all bytes, set address back to 0000
Flip up RUN to start the animation

To adjust the speed:
The speed is controlled by the delay count at address 0x0021-0x0023 (currently 01 00 40 = 4000H).

Faster: Use a smaller value like 01 00 10 (1000H)
Slower: Use a larger value like 01 00 80 (8000H)

The lights will sweep back and forth continuously until you press STOP. Enjoy your Cylon scanner!
