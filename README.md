# TM1638-Driver
A simple STM32 HAL driver for the TM1638 chip. This driver is designed arround the 8 digits, 8 buttons, 8 leds board but can easily be extended to a larger board. 
# Features
`tm1638_DisplayTxt(TM1638 *tm, char *c)` displays a string that has the maximum length of 8 characters with up to 8 additional dots

`tm1638_Led(TM1638 *tm, int position, int on);` sets the led ont the position on or off

`tm1638_Seg(TM1638 *tm, int position, int data)` sends 'data' to the digit on position
