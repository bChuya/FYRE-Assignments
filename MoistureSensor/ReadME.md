# Moisture / Rain Sensor Test Data

This folder contains data collected from the LM393 rain/moisture sensor while it was exposed to different surface conditions. The files are named to describe the state of the sensor at the time of recording, and the measurements show how the sensor output changes as the surface becomes drier, wetter, or partially wiped.

## Data collection script

`rainsensorCODE.py` is the MicroPython script used to read the analog output from the sensor. It:

- connects the sensor to ADC pin A2 / GPIO3
- takes 10 readings at 1-second intervals
- converts the ADC value to an approximate voltage using the formula `voltage = (adc_value / 4095) * 3.3`
- records the reading number, time in milliseconds, ADC value, and voltage
- appends each reading to a CSV file so the data can be analyzed later

The script also creates the CSV file automatically if it does not already exist and continues adding new readings instead of overwriting the old ones.

## Files and what they represent

### `rain_sensorDRY.csv`
This file represents the sensor in a completely dry state. The ADC values stay at the maximum value of 4095, which corresponds to about 3.3 V. This indicates the sensor is not detecting moisture and is behaving like an open or dry surface.

### `HalfWiped.csv`
This file represents a half-wiped / partially wet surface. The readings vary between about 1.06 V and 1.59 V. This shows that the sensor is detecting some moisture, but not a fully wet surface, and the level changes depending on how much water or residue remains on the sensor area.

### `rain_sensorWIPEONSURFACE.csv`
This file represents a light wipe across the surface. The sensor output stays in a lower range, around 0.79 V to 0.87 V, which suggests a small amount of moisture is still present but not enough to create a fully wet condition.

### `rain_sensorENTIRESURFACRWIPED.csv`
This file represents the sensor after the entire surface has been wiped. The values are still low, around 0.69 V to 1.10 V, showing a more uniform and generally wetter condition than the dry state. The readings are lower than dry because the sensor is being affected by moisture or residue spread across the full surface.

### `BlowingONIT.csv`
This file records the sensor while air is being blown on it. Even though the sensor is exposed to airflow, the values remain near the dry condition, around 3.11 V to 3.18 V. This suggests that blowing air alone does not create the same effect as actual moisture on the surface, so the sensor behaves as if it remains dry.

## Summary

The general trend is:

- Dry sensor = high ADC value / high voltage
- Moisture present = lower ADC value / lower voltage
- More moisture or a more evenly wetted surface = lower output values

This makes the CSV files useful for comparing different sensor states and understanding how the LM393 rain sensor responds to varying amounts of water or contamination on its surface.
