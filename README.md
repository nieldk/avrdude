# avrdude
avrdude patches for USBASP as a PDI programmer

Instructions:

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
   
To create a modified usbasp from a cheap usbasp china clone, look here http://szulat.blogspot.com/2012/08/atxmega-programmer-for-050.html
