### ROMDROP
Minimalist Flash Toolkit for the 2006-2015 Mazda MX-5 (NC).

### Requirements:
* Tactrix Openport 2.0 J2534 Device
* Windows 10 (probably works with older versions, but untested)
* NC1/NC2/NC3 Mazda Miata

### How To Download:
* select the green button labeled "clone or download" to the upper right
* select "Download ZIP" from the drop down menu

### Install:
* unzip the romdrop archive to desired location
* license agreement MUST remain in the same folder as the executable

### Application Files:
* romdrop_license.txt - end user license agreement
* romdrop.exe - application executable
* romdrop.crc - checksum data for stock calibrations and patches 
* colormaps (folder) - preferred ecuflash color map files
* logcgfs (folder) - logging configurations for the tactrix
* metadata (folder) - all ecuflash definitions that are currently available
* patches (folder) - available patch files for ROMs currently defined

### Application Files (generated):
* romdrop.log - all loggable activity
* romdrop.rda - last calibration succesful flashed 
* candump.raw - up to 2MB of binary data sniffed off the canbus (see menu item below)

### Usage:
* connect openport into available USB slot
* connect openport to vehicle OBD port 
* double click romdrop.exe to execute from windows
* or execute from command line: romdrop.exe <filename.ext>

BTW you can associate a rom's file extension (typically .bin) with romdrop, afterwhich, you'll only need to double-click the rom you want to flash. Romdrop will automatically attempt to "dynamic" (quick) flash that file to the ECU... no menus, no keypresses, no nothing.

It’s advised that you do not simultaneously run applications that consume heavy resources while flashing.

### Menu Items:
* C | Clear Diagnostic Trouble Codes - self explanatory.
* D | Dynamic Flash ROM - References last succesful flash, and updates ROM blocks that have changed.
* F | Flash Entire ROM - Flashes all ROM blocks to the ECU.
* P | Patch Stock ROM - Many functions accessable by romdrop require that the factory calibration be patched with updated code. Use this option to apply the patch file to your stock ROM, and generate a newly patched calibration for editing with ecuflash.
* R | Read ROM from ECU - this is the first thing you should do if virgin to the application. Why? **You will always want a backup of your original stock rom, and it's required to apply feature patches.**
* S | Sniff CAN Communications - the app can log 2MB of raw CAN communications. This is for the hacker types.
* V | Version for ROM - display ROM patch version
* Q | Quit - Exit application

### Patches:
What are romdrop patches? In order to create a calibration for use with both romdrop and ecuflash, you must first patch your factory rom with a matching '&lt;calibration-id&gt;.patch' file. Don't fret, the process is drag and drop.

* Identify your calibration-id
* Download associated patch (or look in patches directory)
* Launch romdrop
* Select 'P'atch from main menu
* Drag and drop factory rom when prompted
* Drag and drop patch when prompted
* Romdrop will create a newly patched binary

_Note: If no '.patch' can be found for your calibration-id, a definition for your ROM does not exist. Use Romdrop to 'R'ead your factory calibration, then submit a link to the binary for processing. Once processed, a definition (&lt;calibration-id&gt;.xml) and patch (&lt;calibration-id&gt;.patch) will be added to the 'romdrop' and 'romdrop-patches' repositories respectively._

### ECUFlash Setup:
* download and install ecuflash
* navigate to file>options>Directories>Metadata Directory, and set location to romdrop's metadata folder
* navigate to file>options>Directories>Color Map Directory, and set location to romdrop's colomaps fodlder 
* quit and relaunch ecuflash for changes to take effect

