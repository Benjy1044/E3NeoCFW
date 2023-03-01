# E3NeoCFW
Ender-3 (Ender 3 , E3) Neo Custom Firmware

This is a simple firmware that enables a lot of advanced features of marlin for the Ender-3 Neo, This firmware is in active development and will be updated frequently.


## Extra Features

Bed Tramming

Adjust Max Speeds

Jerk

Acceleration

Probe Offsets

Steps

Auto Temp

Safe Probe Z-Homing

High speed probe (Really fast) [Toggle it in the BLtouch menu in configuration]

Assisted tramming

Probe Stow/Deploy in Probe Settings menu

More stability


[Discord Support Server](https://discord.gg/FVmPKeGane)


## Installation Steps
0 - Optional -> write down your current z offset (very useful)

1 - Click release on the right, and download the latest .bin file

2 - Put the .bin file on your micro sd card

3 - Ensuring the printer is fully off plug in the sd card and then turn it on

4 - the screen will be blank for roughly 45 seconds and then you will see the E3CFW logo followed by marling

5 - Press your encoder down, go to "configuration", go to "Advanced Settings" and then press "Initilaize EEPROM" Then "init"

5b - If you followed step 0 you can now go to "Motion" -> "Bed Leveling" -> "Probe Z Offset" -> Insert your value from step 0 press the encoder then go down in the same page to "Store Settings"!

7 - Optional - Enable Power Outage Resume -> "configuration" -> Press on "Power Outage" -> Scroll down and click "Store Settings"


## Setting your Z Offset now!
1 - Auto home the printer (Same method as before CFW)
  Motion -> Auto Home (Wait for it to home)
  Motion -> Move Axis -> Move Z -> 0
  
  Now set the Z offset
  Motion -> Bed Leveling -> Probe Z Offset -> move the dial counter clockwise to lower the nozzle and clockwise to raise it, you want the paper to have a slight   resistance and a slight "ringing" feeling.
  
2 - Now to level the corners!
  Motion -> Bed Leveling -> Bed Tramming (wait for it to home)
  It will now go to the bottom right of your printer, slide a piece of paper under and keep moving the paper whilst loosening & tightening the bed knob until     you get a slight "ringing" feeling / resistance (ENSURE YOU CAN STILL MOVE THE PAPER.
  Press Next and do the same, repeat until you have done all 4 corners at least twice.
  
3 - Auto home once again
  Motion -> Auto Home (Wait for it to home)
  Motion -> Move Axis -> Move Z -> 0
  
  Set the Z offset (it may not have changed but this just dials it in the best)
  Motion -> Bed Leveling -> Probe Z Offset -> move the dial counter clockwise to lower the nozzle and clockwise to raise it, you want the paper to have a slight   resistance and a slight "ringing" feeling.
  
  
## Check if your bed is centered.
  In rare instances your nozzle when the printer reads 110x110 will not be centered (This should not happen but is easy to fix), Grab some masking tape put it on your bed and using a pen draw a cross, Place the bed on your printer and auto home.
  
  After auto home move your axis to X110 Y110 Z1, (If your nozzle is directly where your cross intersects great you can now enjoy printing!
  If it is not centered do not fret, this is easy!
  
  What you want to do is right your starting position down in this case it is X 110 and Y 110
  Now using move axis you want to move your X and Y (1mm increments) until the nozzle is directly over the intersect, and now right down the new values on the    screen, in this case I will pretend my new values are X 136 and Y 140 and now we will do some basic maths
  
x    ( 110-136 = -26)
y    ( 110-140 = -30)

-26 is my x offset
-30 is my y offset

now on your printer go to configuration, Advanced Settings, Probe Offsets and now it's simple you take the value that is currently in the offset and subtract your value from it so in most instances it will now be ( -35-26 = -61 ) -61 is our new offset value so just add it there, do the same for y ( -5-30 = -35)

And store settings, this is a one time step and you will never have to do it again (Unless you reset settings / upgrade firmware)

Once again this issue should not occur, however I wanted to leave a fix just in case.




## Good Gcode is attatched (Auto bed levels each time With fast probing, So doesn't add much onto time at all) (43 seconds on my setup)

[gcode start.txt](https://github.com/Benjy1044/E3NeoCFW/files/10856785/gcode.start.txt)
[gcode stop.txt](https://github.com/Benjy1044/E3NeoCFW/files/10856786/gcode.stop.txt)


## Credits
This is a Marlin based firmware and is maintained by [Benjy1044](https://github.com/Benjy1044)

[Marlin](https://marlinfw.org) is open source.

## Notes
This is for STM32F103RE boards (Creality V4.2.2 - Found on all Ender 3 Neo's)

THIS IS FOR THE ENDER 3 NEO NOT V2 NEO.
