# BLTouch Calibration of the Z-offset

Video Reference: https://www.youtube.com/watch?v=y_1Kg45APko
Pronterface: https://github.com/kliment/Printrun.git

# Step 1
Power on 3D printer, connect to a PC via the USB cable and open Pronterface.

# Step 2
Home 3d Printer using Pronterface

# Step 3
Reset current Z offset to 0.00
M851 Z0

# Step 4
Store Current Setting to Eeprom
M500

# Step 5
Set Eeprom as active parameters
M501

# Step 6
Display current active settings and verify
M503

# Step 7
Home Z axis
G28 Z0

# Step 8
Move Z Axis to 0
G1 F60 Z0

# Step 9
Disable Soft Endstop
M211 S0

# Step 10
Place paper under nozzle and slowly move Z axis down with pronterface until paper is barely able to
move.
Record Z offset (-1.4)
Add paper thickness (.01)

# Step 11
Set printer to new Z offset
M851 Z -X.XX

# Step 12
Turn on Soft Endstops
M211 S1

# Step 13
Save to Eeprom and reload
M500
M501
M503

# GCode
M851 Z0 ;Reset current Z offset to 0.00
M500
M501
M503
G28 Z0
G1 F60 Z0
M211 S0
; Paper test with z axis movement.
; Record offset
M851 Z -1.41
M211 S1
M500
M501
M503

