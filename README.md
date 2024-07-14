# gdc
<!-- [![GitHub release (latest by date)](https://img.shields.io/github/v/release/jnasholm/gdc)](https://github.com/jnasholm/gdc/releases) -->
<!-- ![GitHub last commit](https://img.shields.io/github/last-commit/jnasholm/gdc) -->

# ESP32 Garage Door Controller

Project to create a smart garage door controller for private homes. Brief project description:

- The controller is an [ESP32](https://www.olimex.com/Products/IoT/ESP32/ESP32-DevKit-LiPo/open-source-hardware) programmed with [ESPHome](https://esphome.io/).
- Power supply is 24 VAC from the garage door motor unit.
- Garage door open and closed positions have direct feed-back through [reed switches](https://www.kjell.com/se/produkter/sakerhet-overvakning/larmsystem/detektorer-sensorer-ovriga-tillbehor/magnetkontakt-nc-p50500).
- Opening and closing of the garage door can be done also with existing external switch.
- Option to have garage climate data provided either by the Bosch [BMP280](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp280/) temperature and pressure sensor, or the Bosch [BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/) temperature, humidity and pressure sensor. These sensors are connected to the controllers I<sup>2</sup>C bus with a configurable adress (0x76 or 0x77).

## Description
The controller is designed to be an add-on to an existing garage door motor unit. This project is developed for a Teckentrup TM60, supplied from mains voltage 230 VAC and with an internal transformer to 24 VAC. The external open/close switch is of impuls type which cycles the motor unit between open, stop, close, stop, and so on. No endstop switches were fitted originally, neither a light barrier.

## Home Assistant Lovelace user interface

The following two user interface cards are used to operate the garage door in my installation.

![HASS UI](/images/hass_ui.png)
<br>
*Home Assistant Lovelace example. Button to operate the garage door and position indicators.*

Button to operate the garage door
```yaml
show_name: true
show_icon: true
type: button
tap_action:
  action: toggle
  confirmation:
    text: Manövrera garageport
name: Garageport
icon: mdi:garage-variant
icon_height: 80px
entity: cover.garageport
```
Position indicators
```yaml
show_name: true
show_icon: true
show_state: false
type: glance
entities:
  - entity: binary_sensor.gd_stangd
  - entity: binary_sensor.gd_mellanlage
  - entity: binary_sensor.gd_oppen
state_color: true
```

## Prototype

![Prototype on breadboard](/images/breadboard_prototype.png)
<br>
*Prototype wired on breadboard.*

![Magnet and reed switch](/images/magnet_and_reed_switch.png)
<br>
*Magnet mounted on motor unit runner and one of the end-stop reed switches.*

![Prototype on experiment board](/images/experiment_prototype.png)
<br>
*Prototype on experiment board.*

![Prototype powered for functional testing](/images/prototype_with_regulator_and_leds.png)
<br>
*PPrototype powered for functional testing. Switching regulator on the right, status LEDs on the lower left*
