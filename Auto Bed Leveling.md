# Steps for Autobed leveling (cr10-4s)
1. Open Console to printer (I use octoprint)
2. G28 (home)
3. Move the nozzle to probe location
4. G92 Z10 (turn off softendpoints)
5. Lower until tight
6. M114 (shows current z-height)
7. M851 z<new z-height>
   ex. M851 z-2.361
8. M851 (echo the values
9. M500 (save)
10. G1 Z0 (move the nozzle to home bed - verify paper test)

# Current Z-Offsets

nozzle | z-offset | Notes
--- | --- | ---
.4 mm | -1.808 | stock nozzle
.8 mm | -2.361 | n/a

# Starting G-Code
```
; // Start

G28 ; Homes one time never use this after this point will mess gcode up
M420 S1 ; Load Saved Eeprom From Auto Level
G1 Z5 F3000 ; Lift
G1 X20 Y10 F15000 ; Avoid Clips
G1 Z0.2 F3000 ; Get Ready To Prime Nozzle
G1 X120 E10 F600 ; Prime Nozzle
G1 X150  F5000 ; Wipe Nozzle
```

# Ending G-Code
```
G91
G1 F1800 E-3
G1 F3000 Z10
G90
G28 X0 Y0 ; home x and y axis
M106 S0 ; turn off cooling fan
M104 S0 ; turn off extruder
M140 S0 ; turn off bed
M84 ; disable motors
```

