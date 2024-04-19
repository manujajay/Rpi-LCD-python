# Rpi-LCD-Python

This repository provides guidance and example code for interfacing a Raspberry Pi with an LCD display using Python. It includes instructions for connecting the hardware and scripts for displaying text on the LCD.

## Prerequisites

- Raspberry Pi (any model with GPIO pins)
- LCD display (16x2 or similar)
- Python 3 installed on Raspberry Pi
- GPIO library and Adafruit_CharLCD library

## Installation

Install the required Python libraries for controlling the GPIO pins and the LCD:

```bash
sudo apt update
sudo apt install python3-pip
pip3 install RPi.GPIO
pip3 install adafruit-charlcd
```

## Hardware Setup

1. Connect the LCD pins to the Raspberry Pi GPIO pins.
2. Ensure you have a common ground between the Raspberry Pi and the LCD.
3. Connect the data pins of the LCD (D4-D7) to the corresponding GPIO pins on the Raspberry Pi.
4. Connect the RS and Enable pins to the GPIO pins on the Raspberry Pi.

## Example - Displaying Text on LCD

This example shows how to display text on a 16x2 LCD.

### `display_text.py`

```python
from RPi import GPIO
from adafruit_character_lcd import character_lcd

# GPIO setup
lcd_rs = 26
lcd_en = 19
lcd_d4 = 13
lcd_d5 = 6
lcd_d6 = 5
lcd_d7 = 11
lcd_columns = 16
lcd_rows = 2

# Initialize the LCD
lcd = character_lcd.Character_LCD_Mono(
    lcd_rs, lcd_en, lcd_d4, lcd_d5, lcd_d6, lcd_d7, lcd_columns, lcd_rows
)

# Clear the display
lcd.clear()

# Display text
lcd.message = "Hello, Raspberry Pi!"
```

## Contributing

Contributors who wish to enhance this repository's examples or documentation are encouraged to fork the repository, make their changes, and submit a pull request.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
