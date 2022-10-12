# Temperature Monitoring

## Description

A circuit which will measure temperature from the air around it. It outputs to SMBus, two-wire, or I2C and takes a recommended supply voltage from 1.4V to 3.6V. It will output a voltage that is proportional to the temperature so as the temperature changes so does the voltage. The TMP112-Q1 device features an address pin to allow up to four devices to be addressed on a single bus.

Example: When the temperature in an area is needed to avoid overheating this would be able to tell something that controls the area the temperature and it would then turn it off.

[Datasheet](https://www.ti.com/lit/ds/symlink/tmp112-q1.pdf?){ .md-button target=_blank }

## Accuracy

| Range | Accuracy |
| ----- | -------- |
| -40F to 257F | +/-1.8F |
| 32F to 149F | +/-0.9F |
| -40C to 125C | +/-1C |
| 0C to 65C | +/-0.5C |

## Pins

![](/assets/circuits/tmp112_q1.png)

| Pin No. | Pin Name | I/O | Description |
| ------- | -------- | --- | ----------- |
| 1 | SCL | I | Serial clock. Open-drain output; requires a pullup resistor. |
| 2 | GND | -- | Ground |
| 3 | ALERT | O | Overtemperature alert. Open-drain output; requires a pullup resistor. |
| 4 | ADD0 | I | Address select. Connect to V+, GND, SDA or SCL |
| 5 | V+ | I | Supply voltage, 1.4V to 3.6V |
| 6 | SDA | I/O | Serial data. open-drain output; requires a pullup resistor. |

## Schematic

<script src="https://viewer.altium.com/client/static/js/embed.js"></script>
<div class="altium-ecad-viewer"
  data-project-src="https://spark.docs.iitmotorsports.org/assets/circuits/temperature_monitor.zip"
  style="border-radius: 0px 0px 4px 4px; height: 500px;
         border-style: solid; border-width: 1px;
         border-color: rgb(241, 241, 241);
         overflow: hidden; max-width: 800px;
         max-height: 700px; box-sizing: border-box;">
</div>

## Usage

This circuit is currently not being used in any designs.