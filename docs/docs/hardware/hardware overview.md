# Hardware Overview

Let's take a closer look at the gas sensors and other hardware on these Qwiic breakouts.

## GM-XX2B MEMS Gas Sensors

The GM-XX2B MEMS gas sensors from Winsen are MEMS-based gas sensors that detect concentrations of various gas types. These sensors use a metal-oxide semiconductor (MOS) with an analog output that rises with increases in concentration of gas molecules. The sensing materials have a resistance range that uses a ratio based on the sensor's clean-air resistance value (R<sub>0</sub>) and the sense resistance (R<sub>S</sub>) in a known gas concentration.

### GM-102B Nitrogen Dioxide Gas Sensor

The GM-102B nitrogen dioxide (NO<sub>2</sub>) detects concentrations of nitrogen dioxide in a range of 0.1 to 10 parts per million (ppm). The sensing material resistance (R<sub>s</sub>) has a range of 10K&ohm; to 1,000K&ohm; (in 5 ppm NO<sub>2</sub>) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 2ppm NO<sub>2</sub>)) of &#8804;0.5. Since nitrogen dioxide is an *oxidizing* gas, the resistance increases with gas concentration. Refer to the [datasheet](/ref/datasheets/GM-102B.pdf) for more information on the GM-102B.

### GM-202B Ethanol & Smoke Gas Sensor

The GM-202B ethanol and smoke gas sensor detects concentrations of ethanol in a range of 10 to 1,000 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 1K&ohm; to 30K&ohm; (in 200 ppm of C<sub>2</sub>H<sub>5</sub>OH) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 200 ppm C<sub>2</sub>H<sub>5</sub>OH)) of &#8805;3. Refer to the [datasheet](/ref/datasheets/GM-202B.pdf) for more information on the sensor.

### GM-302B Alcohol/Ethanol Gas Sensor

The GM-302B alcohol/ethanol detects concentrations of alcohol/ethanol in a range of 1 to 500 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 1K&ohm; to 30K&ohm; (in 50 ppm Ethanol) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 5000 ppm Ethanol)) of &#8805;3. Refer to the [datasheet](/ref/datasheets/GM-302B.pdf) for more information.

### GM-402B Combustible Gas Sensor

The GM-402B combustible gas sensor detects in a range of 1 to 10,000 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 1K&ohm; to 30K&ohm; (in 5000 ppm CH<sub>4</sub>) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 5000 ppm CH<sub>4</sub>)) of &#8805;2. Refer to the [datasheet](/ref/datasheets/GM-402B.pdf) for more information on the GM-402B.

### GM-502B VOC Gas Sensor

The GM-502B volatile organic compound (VOC) gas sensor detects common VOCs like ethanol, formaldehyde, acetone and benzene with a detection range of 1 to 500 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 1K&ohm; to 30K&ohm; (in 50 pmm Ethanol) and a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 50 ppm Ethanol)) &#8805;3. Refer to the [datasheet](/ref/datasheets/GM-502B.pdf) for more information on the GM-502B.

### GM-512B Bad Breath Gas Sensor

The GM-512B bad breath sensor detects common compounds found in exhaled breath such as hydrogen sulfide (H<sub>2</sub>S), acetone and alcohol/ethanol. It has a detection range of 0.5 to 50 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 10K&ohm; to 100K&ohm; (in 5 ppm H<sub>2</sub>S) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 5 ppm H<sub>2</sub>S)) of &#8805;2. Refer to the [datasheet](/ref/datasheets/GM-512B.pdf) for more information on the sensor.

### GM-602B Hydrogen Sulfide Gas Sensor

The GM-602B detects concentrations of hydrogen sulfide (H<sub>2</sub>S) with a detection range of 0.5 to 50 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 1K&ohm; to 30K&ohm; (in 50 ppm H<sub>2</sub>S) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 50 ppm H<sub>2</sub>S)) of . Refer to the [datasheet](/ref/datasheets/GM-602B.pdf) for more information on the GM-602B.

### GM-702B Carbon Monoxide Gas Sensor

The GM-702B detects concentrations of carbon monoxide with a detection range of 5 to 5,000 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 1K&ohm; to 30K&ohm; (in 150 ppm CO) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 150 ppm CO)) of &#8805;3. Refer to the [datasheet](/ref/datasheets/GM-702B.pdf) for more information.

### GM-802B Ammonia Gas Sensor

The GM-802B measures ammonia gas concentrations with a detection range of 1 to 300 ppm. The sensing material resistance (R<sub>s</sub>) has a range of 1K&ohm; to 30K&ohm; (in 50 ppm NH<sub>3</sub>) with a sensitivity (R<sub>0</sub>/R<sub>s</sub> (in 50 ppm NH<sub>3</sub>)). Refer to the [datasheet](/ref/datasheets/GM-802B.pdf) for more information on the sensor.

## Power

Power for the breakout is provided either through a Qwiic connection (3.3V/Ground) or through the plated through-hole power pins (3.3V/GND). 

### LDO Power Regulator

The gas sensor breakouts include a LDO power regulator with a variable output that supply the sensor heater with the correct voltage. The boards use one of four resistor values on the regulator's output to set it to either 1.9, 2.0, 2.4 or 2.5V depending on the sensor heater's supply voltage range.

## Connectors

### Qwiic

The board has a pair of Qwiic connectors to power the board with 3.3V and communicate over I<sup>2</sup>C.

### Plated Through-Hole

The breakout includes a six pin 0.1"-spaced plated through-hole (PTH) header that routes out the power (3.3V/GND) and communication I<sup>2</sup>C (SDA/SCL) pins. This header also breaks out the gas sensor's analog voltage output and the ADC's alert pin for users who want to measure the raw output or trigger an alert on specific events.

## Analog to Digital Converter

The Gas Sensor breakout uses the ADC101C021 10-bit Analog-to-Digital Converter (ADC) IC to translate the analog voltage output from the sensor to a digital output over I<sup>2</sup>C. 

## LED

The sole LED on these breakouts is the red Power status LED. This illuminates whenever the board has power.

## Solder Jumpers

The board has four solder jumpers labeled <b>LED</b>, <b>I<sup>2</sup>C</b>, <b>ADR1</b> and <b>ADR2</b>. The <b>LED</b> jumper completes the power LED circuit and is CLOSED by default. Open it to disable the power LED. The <b>I<sup>2</sup>C</b> jumper pulls the SDA and SCL lines to 3.3V through a pair of 2.2k&ohm; resistors and is CLOSED by default. Completely open this three-way jumper to disable pull-ups.

The <b>ADR1</b> and <b>ADR0</b> jumpers set the I<sup>2</sup>C address for the Analog-to-Digital Converter. These three-way jumpers connect to their respective address pin on the ADC (A1 and A0) and can set each pin to one of three states: FLOAT, GND and 3V3. The table below outlines the nine address settings and their corresponding sensor breakout's default I<sup>2</sup>C address.

| Default Sensor | Address |  ADR1 |  ADR2 |
|:--------------:|:-------:|:-----:|:-----:|
|     GM-102B    |   0x50  | FLOAT | FLOAT |
|     GM-202B    |   0x51  | FLOAT |  GND  |
|     GM-302B    |   0x52  | FLOAT |  3V3  |
|     GM-402B    |   0x54  |  GND  | FLOAT |
|     GM-502B    |   0x55  |  GND  |  GND  |
|     GM-512B    |   0x56  |  GND  |  3V3  |
|     GM-602B    |   0x58  |  3V3  | FLOAT |
|     GM-702B    |   0x59  |  3V3  |  GND  |
|     GM-802B    |   0x5A  |  3V3  |  3V3  |

## Board Dimensions

The Gas Sensor breakouts match the Qwiic breakout standard and measure 1" x 1" (22.5mm x 22.5mm) and have four mounting holes that fit a 4-40 screw.