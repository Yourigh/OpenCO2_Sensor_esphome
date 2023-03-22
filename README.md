# OpenCO2 Sensor esphome config
Esphome config for [OpenCO2](https://github.com/davidkreidler/OpenCO2_Sensor) made by David Kreidler.

# How to upload
1. Connect USB
2. Put device to bootloader mode (BTN0 hold while reset)
3. esphome run OpenCO2.yaml
4. select COMx port.

# What works
* Waking up cor ca. 30s, reading sensor, sending data to Home Assistant and updating display.
* Shutdown on low battery voltage. It displays "DISCHARGED!!!" on the screen and shutsdown. Last data will stay on display.
* Adjustable sleep time (defined in code to 5 minutes now).
* When on charger, it stays on (however charger does not wake up the device - it stays on after it wakes up or after reset).

# What does not work
* LED - the neopixel library does not work with this type of LED. The power enable is commented out in the code. If interested, you can try to fix it. I am not bothered by it, because I want the sensor in low power  mode and sleeping the most of the time.
* Wake up botton - currently no tin use. For constant ON state, I connect it to charger and reset the device with reset button. When on charger, it will not go to sleep.
* Getting time information and updating less at night.
