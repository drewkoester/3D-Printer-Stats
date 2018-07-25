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

