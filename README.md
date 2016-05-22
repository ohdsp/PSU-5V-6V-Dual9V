# [Open Hardware DSP Platform](http://www.ohdsp.org)
## Multi output power supply for OHDSP
### Revision 1.1
###### PSU-5V-6V-Dual9V (KiCad 4.0.2-stable)
---
# README
### Disclaimer
Copyright Paul Janicki 2016

Licensed under the TAPR Open Hardware License (www.tapr.org/OHL)

This documentation is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE.

### What is this repository? ###

**Quick summary**

This is a power supply for use with OHDSP boards.

This power supply requires a single 9Vac input (around 500mA should be sufficient for simple systems). 

This power supply outputs one 5V, one 5V or 6V, and +/-9V. Be warned that each of the 5V and 6V rail should be able to deliver higher currents (up to 1A) without issue, but this will overload the input if you are not careful.

This repository contains the KiCad design files, manufacturing Gerber/drill files, and PDF/drawing files for this board.


### How do I get set up? ###

**Summary of set up**

1. Set your self up a directory on a local disk, something simple will make life easier (eg C:\Electronics on Windows as used here), but anywhere will do just fine.
2. Download the Kicad-Libs from [https://github.com/ohdsp/KiCad-Libs](https://github.com/ohdsp/KiCad-Libs) and place in C:\Electronics\Kicad-Libs (or your chosen folder)  
3. Create a OHDSP subdirectory in C:\Electronics (so C:\Electronics\OHDSP)
3. Download this project to C:\Electronics\OHDSP\PSU-5V-6V-Dual9V
4. Fire up Kicad
5. Open the main project file C:\Electronics\OHDSP\PSU-5V-6V-Dual9V\Schematics\PSU-5V-6V-Dual9V.pro
6. (Optional) Setup Pcbnew component library as below.
7. Do as you wish with the project, just keep it under TAPR Open Hardware License

Make sure your git setup doesn't exclude files used in the project (like .LIB files) or things may go wrong down the line.

**KiCad Library Configuration**

Note that you need to setup a Pcbnew library, but the eeschema libraries should work without any changes if you followed the instructions above.

To setup Pcbnew libraries:

In Pcbnew go to Preferences -> Footprint Libraries Manager. Under Global Libraries tab in the top list check if there is a nickname "MyKiCadLibs-Footprints" (usually at the end of the list). If there is but it points to the wrong place then change the Library Path to point to MyKiCadLibs-Footprints (eg C:\Electronics\KiCad-Libs\MyKiCadLibs-Footprints.pretty) folder for your setup. If this is missing you can use "Append with Wizard", choose "Files on my computer", click next, browse to library location (eg C:\Electronics\KiCad-Libs\MyKiCadLibs-Footprints.pretty) and select the folder MyKiCadLibs-Footprints.pretty, click next, check the Status column states OK and the Format is KiCad (if not re-download the library) and click next, then select "To global library configuration..." and click Finish.


To setup eeschema component libraries:
Either from KiCad project window go to Tools -> Run Library Editor OR under eeschema, go to Tools -> Library Editor. Then Preferences -> Component Libraries.

The top section "Component Library Files" should ideally contain only two libraries, the "power" library that ships with KiCad and "MyKiCadLibs-Lib" available from above. To setup MyKiCadLibs-Lib as a relative path under the "User defined search path" click add. Browse to the location of KiCad-Libs you download above (eg C:\Electronics\KiCad-Libs) and click "Select Folder". Say yes to add a relative path. Under component library files click add, browse to the KiCad-libs again (eg C:\Electronics\KiCad-Libs), select file "MyKiCadLibs-Lib.lib" and click open. MyKiCadLibs-lib should appear in the component library list with no path as it will be using the user defined search path set in the box below. 

