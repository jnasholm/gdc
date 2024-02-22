# ESP32 pin schema

The controller IO pins are assigned according to the table below[^1][^2][^3].

|Function|Pin|Comment|
|------------------------------|:--:|--------|
|Garage door closed sensor|16|
|Garage door open sensor|17|Used for ethernet port if enabled
||18|Used for ethernet port if enabled
|External open/close switch|19|
|Garage door relay open/close|21|
||23|Used for ethernet port if enabled
|Climate sensor i2c SDA|26|
|Climate sensor i2c SCL|27|
|System status LED|32|
|Controller status LED|33|
|Battery voltage|35|May require soldering on the ESP32 board to enable|
|Charging voltage|39|May require soldering on the ESP32 board to enable|

[^1]: [ESP32-Devkit-Lipo GPIOs map](https://www.olimex.com/Products/IoT/ESP32/ESP32-DevKit-LiPo/resources/ESP32-DevKit-Lipo-GPIOs.png)
[^2]: [ESP32-POE-ISO GPIO map](https://www.olimex.com/Products/IoT/ESP32/ESP32-POE-ISO/resources/ESP32-POE-ISO-GPIO.png)
[^3]: [ESP32 Pinout Reference: Which GPIO pins should you use?](https://randomnerdtutorials.com/esp32-pinout-reference-gpios/)
