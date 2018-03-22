### ROMDROP/NC
Minimalist PCM flash utility for the NC Mazda MX-5 (Miata). 

### Requirements:
* Tactrix Openport 2.0 J2534 Device
* Windows (compiled with Win10, other windows versions untested)
* NC1/NC2/NC3 Miata

### Install:
* Unzip the romdrop archive to desired location
* License agreement MUST remain in the same folder as the executable

### Application Files:
* romdrop_license.txt - End User License Agreement
* romdrop.exe - application executable
* metadata (folder) - All ECUFlash definitions that are currently available.
* colormaps (folder) - Preferred ECUFlash color map files

### Application Files (generated):
* romdrop.log - All loggable activity. If something goes awry for whatever reason, copy this log file to submit for analysis.
* candump.raw - raw binary data sniffed off the canbus

### Usage:
* connect Openport into available USB slot
* connect Openport to vehicle OBD port 
* double click romdrop.exe to execute from windows
* or execute from command line: romdrop.exe <filename.ext>

BTW you can associate a rom's .bin or .hex extension with romdrop, afterwhich, you'll only need to double-click the rom you want to flash. Romdrop will automatically attempt to "data" (quick) flash that file to the ECU... no menus, no keypresses, no nothing.

It’s advised that you do not simultaneously run applications that consume heavy resources while flashing. Doing so can impact USB speeds which can result in a failed flash (BTW, a failed flash and all it's blinking lights isn’t the end of the world... it's recoverable).

### Menu Items:
* Clear DTCs (self explanatory)
* Flash DATA block only - this is a quick flash option. Only the core data blocks of the ecu are flashed. This cuts down flash times tremendously based on generation. NC1 are ~30s, and NC2/3 are ~20s. 
* Flash Entire ROM - If a patch has been applied to one of the rom’s routines, the changes will tend to exist in an area not touched by the “Flash Data Block Only” command.  Under these circumstances, this option exists to flash the rom in it’s entirety. There are a few instances where defined data exists outside of the core data blocks as well. In those rare cases, a full flash is recommended as well. Flash times are ~90s.
* Read ROM from ECU - this is the first thing you should do if you’re virgin to the application. Why? You always want a backup of your original rom. Keep it safe, just in case you need to revert back to stock. Also it’s a good way to test communications between the app and your vehicle.
* Sniff CAN Communications - The app can log 2MB of raw CAN communications. This is for the true hacker types.
