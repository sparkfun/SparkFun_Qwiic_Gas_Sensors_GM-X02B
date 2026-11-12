# Troubleshooting

## Sensor Performance

These gas sensors all use a metal-oxide semiconductor to measure gas concentration and require a warm-up period of a few minutes before readings will settle. Perform this warm-up period on first power up and after the sensor has been powered off for 24-168 hours. It's also recommended to configure and set the clean air (R0) resistance value. The second example in the Arduino library covers how to set that value. For non-demo applications, For a save the measured R0 (e.g. to EEPROM) and restore it with `setCleanAirResistance_Ohm()` instead of recalibrating on every boot.

## Qualitative vs Quantitative Data

Due to these sensors' design and measurement constraints, the values for measured gases are not calibrated and measurements can have some crossover with other gases. Each sensor reacts strongest to the sensor's specified gas concentrations and in order to get useful, quantitative data in ppm, it requires calibrating the sensor output with known concentrations of the gas (or gases).

## Support

If you need technical assistance or more information on a product that is not working as you expected, we recommend heading on over to the [SparkFun Technical Assistance](https://www.sparkfun.com/technical_assistance) page for some initial troubleshooting.

If you need technical assistance and more information on a product that is not working as you expected, visit the [SparkFun Community](https://community.sparkfun.com). The community forums are monitored by the SparkFun Technical Support Team and the SparkFun community as a whole. If this is your first visit to our forum, you'll need to create a [Forum Account](https://forum.sparkfun.com/ucp.php?mode=register) to post questions.

        