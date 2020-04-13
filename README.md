# avrdude for USBASP-PDI

In order to use avrdude for USBASP-PDI you will also need to patch avrdude to understand how to use it.

## Instructions:
```
1. Download AVRDUDE from official sources
   $ wget http://download.savannah.gnu.org/releases/avrdude/avrdude-6.3.tar.gz

2. Extract downloade AVRDUDE
   $ tar xvf avrdude-6.3.tar.gz
   
2. change to avrdude directory
   $ cd avrdude-6.3

3. Apply patches
   $ patch -i usbasp.c.diff
   $ patch -i usbasp.h.diff
   $ cp <path/to/xmega_pdi.h> .
   $ ./bootstrap
   $ ./configure
   $ make

4. Now you can run avrdude like this (flash.hex needs to be replaced with your file)
   write flash: $ ./avrdude -c usbasp -p x32a4u -U flash:w:flash.hex:i
   read flash to file (flash.bin is raw binary here): $ ./avrdude -c usbasp -p x32a4u -U flash:r:flash.hex:r

Caveat: It seems libusb have issues on 64 bit Linux OS, so you may experience that you need to use a Windows box instead of Linux. Compilation for that is available, but I have attached a working binary in releases.
