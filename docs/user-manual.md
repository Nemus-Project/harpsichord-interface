## Layout

The controller board and what everything is

| ![ ](./img/controller_board_labelled.png) |
| :---------------------------------------: |
|             Controller Board              |


Parts labelled are:

- SPI FRAM
- External reset JST Socket
- Rotary Encoder JST Socket
- Onboard Reset Button
- Arduino Nano
- Sensor Ribbon Cable
- DC Barrel Socket

## Calibration

The calibration process

1. Plug in powersupply: a 5V supply using the barrel jack.
2. connect USB cable to a computer with Ardunio IDE installed.
3. Open Arduino IDE and use serial plotter


> [!NOTE] 
> The the data sent conforms to the labelled printing standard of the
> [serial plotter](https://docs.arduino.cc/software/ide-v2/tutorials/ide-v2-serial-plotter/),
> as such any serial connection can be used. A limitation of the serial plotter is
> that only 6 streams of information can be printed. Using a separate environment
> printing enviornment and editing the firmware may yield a more versatile system.
> Processing would be an obvious candidate or
> [`juce_serialport.h`](https://github.com/cpr2323/juce_serialport) if this
> functionality is to be integrated with a digital instrument.


|       Mode        | LED Colour |
| :---------------: | :--------: |
|    Key Select     |    Blue    |
|  Pluck Threshold  |   Green    |
| Release Threshold |   Purple   |

In addition, a `p` character can be sent over the serial connection to activate and deactivate printing.

Printing can slow the process of reading and sending MIDI data. This should be deactivated during playing.

## Troubleshooting

### Some Sensor Boards Not Responding
### Sensor Thresholds Have changed

Check that the correct supply is plugged in _and_ switched on. The Arduino Nano has a regiulated 3.3V power line that is used for the LEDs, rotary and FRAM. The sensors use the 5V power directly. Incorrect or absent power will result in a change of thresholds and some sensors may not respond as they try and draw 5V from the Arduino.
