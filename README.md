# Stationeer Scripts
Scripts I've written for Stationeers. I've enjoyed automating base functions with the IC10 chip and the game's implementation of MIPS pseudo-assembly, and this is my dump of programs that I've written. Perhaps others will find them usefull.

## Notes
### filter-manager

Manages turning on and off a filter for each type of gas that is important, saving energy. Pollutant (X) will have to be handled by the reader, since it isn't really needed by much beyond an AC system. Currently triggers filtration when at least 1kmol of a supported gas in the connected "waste" system, and uses a sleep statement to provide hysteresis. 


### gas-mixer

Manages two gas mixers via batch mode for creating a mix of N, O2, and CO2 suitable for use in a habitat or greenhouse. Mixers turn when the pressure is below at 20MPa, and turn off when it goes above 2MPa. Place this setup with some gas storage behind a pressure regulator for best results.


### power-display

Simple script that reads a cable analyzer on the charging and discharging sides of a battery and then displays the inbound current, charge percentage, and outbound current in sequence.

Future ideas:
- Read `PrefabHash` from the battery device to support batch reading in Average mode, regardless of type or count of station battery connected

### solid-generator-mgmt

Simple start / stop script for a solid fuel generator.

Future ideas:
- Read `PrefabHash` from the battery device to support batch reading in Average mode, regardless of type or count of station battery connected

### vacuum-gas-generator-mgmt

Script to start / stop a gas fuel generator in a vacuum, such as the moon. Uses an AC unit with 2+ radiators for cooling.

Assumptions
- Generator is in a 2x1 building
- Atmosphere in this build is at least 50 kpa (I usually use CO2, since there's usually plenty of it from the furnaces)
- Using 33% O2 / 66% Vol fuel mix
