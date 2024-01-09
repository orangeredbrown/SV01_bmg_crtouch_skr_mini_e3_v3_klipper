# SV01_bmg_crtouch_skr_mini_e3_v3_klipper
This is my base config for getting klipper working on a SV01 (original) with a BMG extruder, CRTouch probe, with a skr mini e3v3.

I wanted to post this out there for anyone else looking to klipperize their OG SV01. It took a lot of digging to compile this, and it's pretty basic.

I will be adding a lot of extra macros and whatnot, but this config got me up and running printing beautiful prints. 

You'll want to PID tune and find your z-offset, as well as tweak some things, but this should get the following up and running:

Stock LCD screen
Extruder
Motors
CRTouch

I am running prusaslicer, make sure to add something like this to your start g-code:

M104 S0

M140 S0
SET_HEATER_TEMPERATURE HEATER=heater_bed TARGET=60

SET_HEATER_TEMPERATURE HEATER=extruder TARGET=200
G28
print_start EXTRUDER=[first_layer_temperature[initial_extruder]] BED=[first_layer_bed_temperature] HEIGHT=[first_layer_height] LAYER=[layer_height] FILAMENT=[filament_type] EXTRUSION=[extrusion_width] 
