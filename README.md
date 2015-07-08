# HeaterBreaker
Code for an MCU to watch for temperatures exceeding cutoff ranges.

# Features
- Min/Max cutoff temps. 
- Just insert in between hotend/heated bed output and hotend/heated bed
- LED indicator of status
- Stays off if upper cutoff temp tripped more than configured threshold within a period of time.  

# How it works, what it does
Runaway hotend is a concern, if the hotend were left to keep rising in temp, it presents a fire hazzard.

This module sits between the printer control board and the hotend, adding another on/off switch in the chain.
The microcontroller takes reading from its own thermistor to determine if a cutoff temperature is exceeded.
The Min cutoff is to catch if the thermistor is disconnected.
The Max cutoff is to catch if the temp exceeds what has been programmed as a safe upper limit.
Multiple trips within a period of time could catch if the printer main board is hung and is still powering the hot end. If this is the case, the board will just cutoff power to the hotend until it is reset.
