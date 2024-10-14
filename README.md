# Mad_PlantBug

Low-power capacitive soil moisture sensor with BLE connectivity.

## Features

* powered via CR2032 coin battery
* transmits telemetry via BLE
* measures ambient light and temperature
* visual indication via LED

Top             |  Bottom
:-------------------------:|:-------------------------:
![](pictures/top.svg)  |  ![](pictures/bottom.svg)

## How it works

This sensor determines the amount of soil moisture by measuring changes in capacitance of the probe submerged in soil.\
Insertable part forms a parasitic coplanar capacitor which uses soil as a dielectric medium.\
As the environment around the capacitor changes depending on whether the soil becomes wetter or drier, so does it capacitance.\
Together with a resistance the probe forms an RC low-pass filter.\
Changes in capacitance shape the output waveform observed by the sensor.
\
Measurement pipeline logic is as follows:\
`environment changes -> capacitance changes -> cutoff frequency changes -> peak amplitude changes`

## Capacitance measurement
* Clean PCB measurement in air: ~59pF
* Fully submerged in water: 2nF
<details><summary>Assembly & measurements</summary>
<p>
<img src="pictures/assembled.jpg" width="400" title="Powered on">
<img src="pictures/submerged.jpg" width="400" title="Submerged in water">
</p>
</details>
