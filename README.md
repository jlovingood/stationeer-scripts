# Stationeer Scripts
Scripts I've written for Stationeers. I've enjoyed automating base functions with the IC10 chip and the game's implementation of MIPS pseudo-assembly, and this is my dump of programs that I've written. Perhaps others will find them usefull.

## Notes
### filter-manager

Manages turning on and off a filter for each type of gas that is currently important, saving energy. Pollutant (X) will have to be handled by the reader, since it isn't really used beyond an AC system. Currently triggers filtration when at least 1kmol of a supported gas in the connected "waste" system, and uses a sleep statement to provide hysteresis. 


### gas-mixer

Manages two gas mixers via batch mode for creating a mix of N, O2, and CO2 suitable for use in a habitat or greenhouse. Mixers activate when the pressure in the hab air storage falls below 2MPa, and deactivate when it rises above 20MPa. Preset the mixes you want on the mixers manually. Place this setup behind a regulator with some gas storage for best results. Managing the temperature of the gasses is up to the user. 


### power-display

Simple script that reads a cable analyzer on the charging and discharging sides of a battery and then displays the inbound current, charge percentage, and outbound current in sequence.

TODO:
- Read `PrefabHash` from the battery device to support batch reading in Average mode, regardless of type or count of station battery connected
- Calculate an estimated run time and display it

### solid-generator-mgmt

Simple start / stop script for a solid fuel generator.

TODO:
- Read `PrefabHash` from the battery device to support batch reading in Average mode, regardless of type or count of station battery connected

### vacuum-gas-generator-mgmt

Script to start / stop a gas fuel generator in a vacuum, such as the moon. Uses an AC unit with 2+ radiators for cooling.

Assumptions:
- Generator is in a 2x1 building
- Atmosphere in this build is at least 50 kpa (I usually use CO2, since there's usually plenty of it from the furnaces)
- Using 33% O2 / 66% Vol fuel mix
