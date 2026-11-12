# Arduino Examples

## Sensor Selection

This library works for all nine of the GM-XX2B gas sensor breakouts by selecting the board at the beginning of each example. Make sure comment/uncomment the correct board from this section of code:

``` c++
// SfeGM102BArd mySensor;   // GM-102B - nitrogen dioxide (NO2)
// SfeGM202BArd mySensor;   // GM-202B - alcohol, smoke
// SfeGM302BArd mySensor;   // GM-302B - ethanol
// SfeGM402BArd mySensor;   // GM-402B - methane, propane
// SfeGM502BArd mySensor;   // GM-502B - VOCs
// SfeGM512BArd mySensor;   // GM-512B - breath odor
SfeGM602BArd mySensor;      // GM-602B - hydrogen sulfide (H2S)
// SfeGM702BArd mySensor;   // GM-702B - carbon monoxide (CO)
// SfeGM802BArd mySensor;   // GM-802B - ammonia (NH3)
```

## Example 01 - Basic Readings

The first example shows how to initialize a single sensor and read the data from it once per second to print the raw ADC value, sensor output voltage and the sensing element resistance (R<sub>s</sub>). Open the example by navigating to **File** > **Examples** > **SparkFun GM-X02B Arduino Library** > **Example01_BasicReadings**.

Make sure to select the correct sensor in the `mySensor` selection outlined above then select your Board and click the "Upload" button. After the code finishes uploading, open the [serial monitor]() with the baud set to **115200**. The example starts by initializing the selected sensor on the I<sup>2</sup>C bus and prints out the sensor's name, target gas, I<sup>2</sup>C address and detection range in ppm. Give the sensor a few minutes to warm up for readings to settle. After readings settle, it prints out the raw sensor ADC value, voltage and resistance once every second.

## Example 02 - Clean Air Response

Example 2 measures the sensor's clean-air resistance (R0) at startup, then reports the gas response continuously. This example uses the `getGasResponse()` function so relative gas measurement works identically on every GM-xx2B variant. The `getGasResponse()` function uses either R0/R<sub>s</sub> on parts with falling resistance and R<sub>s</sub>/R0 on parts with rising resistance (GM-102B only). This setting makes it so the value sits near 1.0 in clean air and rises with the target gas for all nine gas sensors.

Make sure to run this example in known clean air with the sensor fully warmed up. The example defaults to warm the sensor up for three minutes before taking the clean air reference value. If the board has been powered off for a long time, preheat the sensor first for the time period specified in your sensor's datasheet. For an actual application, save the measured R0 (e.g. to EEPROM) and restore it with `setCleanAirResistance_Ohm()` instead of recalibrating on every boot.

The example sets a flag for an elevated reading. Adjust this value for your environment:

``` c++
const float kDetectResponse = 1.5;
```

`getRatedSensitivity()` works as reasonable upper anchor (the response this part is specified to reach at its rated ppm).

Depending on your sensor, you'll want to adjust the warmup period. The example defaults to three minutes for a quick demo but longer is better:

``` c++
const unsigned long kWarmupMillis = 3UL * 60UL * 1000UL;
```

## Example 03 - Gas Alert Threshold

The third example shows how to configure a threshold for the ADC to flag (or optionally trigger an interrupt on the Alert pin) when measurements cross that threshold. This example uses the `setGasAlertResponse()` function to set a threshold of 2.0 (twice the clean air measurements).

## Example 04 - Peak Tracking

The fourth example shows how to use the ADC's low and high conversion registers to track peaks of gas concentrations. Which register holds "most gas" depends on the part. On the eight reducing-gas sensors, more gas means lower Rs and a HIGHER output voltage, so peak gas is the highest conversion. On the GM-102B (NO2) it is the opposite, and peak gas is the LOWEST conversion. `getPeakGasVoltage_V()` and `clearPeakGasCounts()` pick the right register for you; `getLowestConversion()` and 1getHighestConversion()1 remain available if you want the raw registers.

## Example 05 - Multiple Sensors

The sixth example shows how to set up and read measurements from three gas sensors on the same I<sup>2</sup>C bus. This example only uses three but since all nine of the GM-XX2B sensors have unique addresses you could put all of them in the configuration array. Each object declares its own part, so each one gets the right address, the right load resistance (the GM-102B board carries 68.1k rather than the  family's 4.7k), and the right curve direction. 

``` c++
SfeGMX02BArd sensors[] = {
    SfeGMX02BArd(GM_602B), // H2S at 0x58
    SfeGMX02BArd(GM_702B), // CO  at 0x59
    SfeGMX02BArd(GM_102B), // NO2 at 0x50, resistance RISES with gas
};
```