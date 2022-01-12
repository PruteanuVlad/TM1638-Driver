## TM1638-Driver
A simple STM32 HAL driver for the TM1638 chip. This driver is designed arround the 8 digits, 8 buttons, 8 leds board but can easily be extended to a larger board. 

## Installation

Download the header and source files and add them to your STM32 project. Don't forget to include the header file in your code.

## Features

`tm1638_DisplayTxt(TM1638 *tm, char *c)` displays a string that has the maximum length of 8 characters with up to 8 additional dots

`tm1638_Led(TM1638 *tm, int position, int on);` turns the led on the specified position on or off

`tm1638_Seg(TM1638 *tm, int position, int data)` sends 'data' to the digit on the specified position

`tm1638_DisplayClear(TM1638 *tm)` clears the display

`tm1638_TurnOn(TM1638 *tm, uint8_t brightness)` turns the display on at the specified birghtness level

`tm1638_Draw(TM1638 *tm)` allows the users to turn individual segments on and off using the integrated buttons

## Examples
```c
//...
#include "TM1638.h"
//...
int main(void)
{
  //...
  TM1638 TM;
  TM.clk_port= CLK_GPIO_Port;
  TM.clk_pin = CLK_Pin;
  TM.stb_port= STB_GPIO_Port;
  TM.stb_pin = STB_Pin;
  TM.dio_port= DIO_GPIO_Port;
  TM.dio_pin = DIO_Pin;
  TM.vcc_port= VCC_GPIO_Port;
  TM.vcc_pin = VCC_Pin;
  tm1638_Draw(&TM);
  //...
}
//...
```
## Error codes
- Error 1: invalid brightness value
- Error 2: text message too long
- Error 3: invalid led position
- Error 4: invalid led command
- Error 5: invalid digit position
- Error 6: invalid digit command
- Error 7: invalid character 
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)
