# gdc
<!-- [![GitHub release (latest by date)](https://img.shields.io/github/v/release/jnasholm/gdc)](https://github.com/jnasholm/gdc/releases) -->
<!-- ![GitHub last commit](https://img.shields.io/github/last-commit/jnasholm/gdc) -->

# ESP32 Garage Door Controller

Project to create a smart garage door controller for private homes. Brief project description:

- The controller is an [ESP32](https://www.olimex.com/Products/IoT/ESP32/ESP32-DevKit-LiPo/open-source-hardware) programmed with [ESPHome](https://esphome.io/).
- Power supply is 24 VAC from the garage door motor unit.
- Garage door open and closed positions have direct feed-back through [reed switches](https://www.kjell.com/se/produkter/sakerhet-overvakning/larmsystem/detektorer-sensorer-ovriga-tillbehor/magnetkontakt-nc-p50500).
- Opening and closing of the garage door can be done also with existing external switch.
- Option to have garage climate data provided either by the Bosch [BMP280](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp280/) temperature and pressure sensor, or the Bosch [BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/) temperature, humidity and pressure sensor.

## Description
The controller is designed to be an add-on to an existing garage door motor unit. This project is developed for a Teckentrup TM60, supplied from mains voltage 230 VAC and with an internal transformer to 24 VAC. The external open/close switch is of impuls type which cycles the motor unit between open, stop, close, stop, and so on. No endstop switches were fitted originally, neither a light barrier.

