# stride_vmd
updating stride to work with lipoproteins


In order to install stride on a Unix/Linux system with gcc follow these steps. Other compilers need slight modifications of the Makefile.

    Download the stride stand-alone program source code
    Create a directory wherever/stride and copy the tar ball there
    Unpack the tar ball: tar -zxf stride.tar.gz
    Compile stride: make
    Now you have a binary file stride in your directory, you can copy it to /usr/local/bin or add the current directory to your path to use it system-wide






STRIDE

STRIDE is used by VMD to compute the secondary structure given the protein 3D coordinates. The appropriate STRIDE binary is included in the VMD binary distribution. To compile it yourself, see the web site at
http://www.embl-heidelberg.de/stride/stride_info.html for information on how to get the source and see ./lib/stride for information on how to use it with VMD.

Change line 43 of stride.h from

   #define MAX_AT_IN_RES             50

to

   #define MAX_AT_IN_RES             75

because there are many structures with non-standard residues containing more than 50 atoms.

Change line 96 of stride.c from

   return(SUCCESS);

to

   return(0);

since a program should return 0 if everything ended correctly.




replace /usr/local/lib/vmd/stride...... with new version
