### ROMDROP
Minimalist PCM Flash Toolkit for the 2006-2015 Mazda MX-5 (NC).

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
* metadata (folder) - all ecuflash definitions that are currently available.
* colormaps (folder) - preferred ecuflash color map files

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

It’s advised that you do not simultaneously run applications that consume heavy resources while flashing. Doing so can impact USB speeds which can result in a failed flash. BTW, a failed flash and all it's blinking lights isn’t the end of the world... in most cases, it's recoverable.

### Menu Items:
* C | Clear Diagnostic Trouble Codes - self explanatory.
* D | Dynamic Flash PCM - References last succesful flash and updates blocks that have changed.
* F | Flash ROM - Flashes all ROM blocks to the PCM/ECU.
* P | Patch Stock ROM - Many functions accessable by romdrop require that the factory calibration be patched with updated code. Use this option to apply the patch file to your stock ROM, and generate a newly patched calibration for editing with ecuflash.
* R | Read ROM from ECU - this is the first thing you should do if virgin to the application. Why? **You will always want a backup of your original stock rom, and it's required to apply feature patches.**
* S | Sniff CAN Communications - the app can log 2MB of raw CAN communications. This is for the true hacker types.

### ECUFlash Setup
* download and install ecuflash
* navigate to file>options>Directories>Metadata Directory, and set location to romdrop's metadata folder
* navigate to file>options>Directories>Color Map Directory, and set location to romdrop's colomaps fodlder 
* quit and relaunch ecuflash for changes to take effect
