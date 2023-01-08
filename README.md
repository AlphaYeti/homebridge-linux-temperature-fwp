# homebridge-linux-temperature-fwp

A homebridge temperature sensor for Firewalla Purple Linux temperatures.
Based on the fork by Chris Jones at https://github.com/cmsj/homebridge-linux-temperature
Based on the fork by Peter Harry at https://github.com/GreyPeter/homebridge-pi-lm75
Based on origial code by Mark Webb-Johnson <mark@webb-johnson.net>.
See original code here: https://github.com/markwj/homebridge-pi


# Installation

1. Install Homebridge using: `npm install -g homebridge`
2. Install this plugin using: `npm install -g homebridge-linux-temperature-fwp`
3. Update your Homebridge `config.json` using the sample below.

# Configuration

```json
{
  "accessory": "LinuxTemperature",
  "name": "Core 0 Temperature",
  "sensor_path": "/sys/class/thermal/thermal_zone0/temp",
  "divisor": 1000
},
{
  "accessory": "LinuxTemperature",
  "name": "Core 1 Temperature",
  "sensor_path": "/sys/class/thermal/thermal_zone1/temp",
  "divisor": 1000
}
```

Fields:

* `accessory` must be "LinuxTemperature" (required).
* `name` is the name of the published accessory (required).
* `sensor_path` is the path to a file (typically in `/sys` or `/proc` that contains just the temperature value (required).
* `divisor` is the amount to divide the temperature value by (e.g. typically Linux provides milli-degrees, so a divisor of 1000 gives degrees)

