# USB Isolator based on ADuM3160
Defective USB devices can destroy the USB port or even the motherboard of your PC. Special devices, such as a USB killer, actually serve this purpose. Furthermore, measuring devices with a USB connection can deliver incorrect measurement results due to ground loops, or even cause short circuits. This 2.5kV USB 2.0 Isolator with 200mA power supply and full speed (12Mbps) support is a simple solution to these problems.

- Design Files (EasyEDA): https://easyeda.com/wagiminator/adum3160-usb-isolator

![USB-Isolator_pic1.jpg](https://raw.githubusercontent.com/wagiminator/ADuM3160-USB-Isolator/main/documentation/USB-Isolator_pic1.jpg)

# Hardware
## ADum3160 USB Isolator IC
The ADuM3160 is a 2.5kV USB port digital isolator. Combining high speed CMOS and monolithic air core transformer technology, this isolation component provides outstanding performance characteristics and is easily integrated with low and full speed USB-compatible peripheral devices.

Many microcontrollers implement USB so that it presents only the D+ and D− lines to external pins. This is desirable in many cases because it minimizes external components and simplifies the design; however, this presents particular challenges when isolation is required. Because the USB lines must switch between actively driving D+/D− and allowing external resistors to set the state of the bus, the ADuM3160 provides mechanisms for detecting the direction of data flow and control over the state of the output buffers. Data direction is determined on a packet-by-packet basis.

The isolator has a propagation delay comparable to that of a standard hub and cable. It operates with the bus voltage on either side ranging from 4.5 V to 5.5 V, allowing connection directly to
V_BUSx by internally regulating the voltage to the signaling level. The ADuM3160 provides isolated control of the pull-up resistor to allow the peripheral to control connection timing. The device draws low enough idle current that a suspend state is not required.
The 5kV reinforced insulation version, the ADuM4160, can also be used with this board.

Features:
- Compatible with USB 2.0 full speed (12Mbps)
- Bidirectional communication
- VBUS operating voltage: 4.5V to 5.5V
- 8mA maximum upstream supply current at 12Mbps
- 2.3mA maximum upstream idle current
- Upstream short circuit protection
- Class 3A contact ESD performance
- High common mode transient immunity: >25kV/μs

For transient voltage protection, TVS diode arrays are added at the input and the output in addition to the typical serial resistors. Note that the ADuM3160 is hardwired for USB2.0 full speed (12Mbps) support only on this board. Low speed devices may not work.

![USB-Isolator_pic3.jpg](https://raw.githubusercontent.com/wagiminator/ADuM3160-USB-Isolator/main/documentation/USB-Isolator_pic3.jpg)

## HLK-1D0505A Isolation DC/DC Converter
The HLK-1D0505A is a 5V input, 5V output 1W isolation DC/DC converter with small size and high efficiency. It is used to isolate the input from the output power of the device. It features:
- Constant voltage input, isolated unregulated single output, 1W
- Low super power consumption, standby power consumption is only 0.025W (input current 5mA)
- Input and output isolation withstand voltage 1500VDC
- Low ripple/noise <50mVpp
- Conversion efficiency up to 88% (Typ)
- Good output short circuit and over current protection with self-recovery
- High reliability, long life design, continuous work >100000 hours
- Potted with high-quality environmentally friendly waterproof and thermal conductive glue, moisture-proof and vibration-proof, and meets the IP65 standard

The output voltage is not regulated. The load at the output of the converter must be at least 10% of the specified maximum load, in this case 20mA, as otherwise the output voltage could rise significantly above 5.5V, which would damage the ADuM3160 or the connected device. A 5.1V Zener diode in connection with a small resistor provides this load if the voltage is too high. Without a connected downstream device, the maximum output voltage is limited to about 5.3V this way.

![USB-Isolator_pic2.jpg](https://raw.githubusercontent.com/wagiminator/ADuM3160-USB-Isolator/main/documentation/USB-Isolator_pic2.jpg)

# Characteristics

|Parameter|Value|
|:-|:-|
|USB Type|USB 2.0 full speed 12Mbps|
|Input Voltage|4.5 - 5.5V|
|Output Voltage|4.7 - 5.3V|
|Output Voltage Ripple|30mVpp@100mA|
|Output Current|max 200mA|
|Standby Current|25mA|
|Signal Line Isolation|2.5kV|
|Power Line Isolation|1.5kV|

![USB-Isolator_load.png](https://raw.githubusercontent.com/wagiminator/ADuM3160-USB-Isolator/main/documentation/USB-Isolator_load.png)

# References, Links and Notes
1. [ADuM3160 Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/ADuM3160.pdf)
2. [HLK-1D0505A Datasheet](https://datasheet.lcsc.com/lcsc/1912111437_HI-LINK-HLK-1D0505A_C465411.pdf)
3. [FSRV05-4 Datasheet](https://datasheet.lcsc.com/lcsc/2010262108_FUXINSEMI-FSRV05-4_C908218.pdf)
4. [Analog Devices Circuit Note CN0160](https://www.analog.com/media/en/reference-design-documentation/reference-designs/CN0160.pdf)

![USB-Isolator_pic4.jpg](https://raw.githubusercontent.com/wagiminator/ADuM3160-USB-Isolator/main/documentation/USB-Isolator_pic4.jpg)
![USB-Isolator_pic5.jpg](https://raw.githubusercontent.com/wagiminator/ADuM3160-USB-Isolator/main/documentation/USB-Isolator_pic5.jpg)

# License
![license.png](https://i.creativecommons.org/l/by-sa/3.0/88x31.png)

This work is licensed under Creative Commons Attribution-ShareAlike 3.0 Unported License. 
(http://creativecommons.org/licenses/by-sa/3.0/)
