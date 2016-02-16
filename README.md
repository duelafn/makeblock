
Arduino GCode Parser and Command-Line Tool
==========================================

Unofficial fork of the Makeblock arduino gcode interpreter ready to run on
the most excellent Makeblock
[XY-Plotter](http://www.makeblock.cc/xy-plotter-robot-kit/).

Additionally includes a command-line tool which can send your gcode files
to the plotter without using the Arduino serial connection, and can render
your gcode files to PostScript or other image format (using the `convert`
utility from ImageMagick).


This repository splits the arduino files from the full
[Makeblock repository](https://github.com/Makeblock-official/XY-Plotter-2.0)
since I had no interest in the Java GRemote tool. The exact license of the
arduino `.ino` files is a bit unclear (but at least must be compatible with
the LGPL of the arduino Servo library), there is a
[bug report](https://github.com/Makeblock-official/XY-Plotter-2.0/issues/13)
asking for upstream license clarification.


GCode
-----

This controller supports codes: 0-4, 20, 21, 28, 30, 90, 91, 92.

See http://linuxcnc.org/docs/html/gcode.html for a good GCode reference,
though this controller will never support most of the codes documented
there.

Additionally, this interpreter supports the non-standard G22 to set units to cm.

For PEN UP use: G1 Z0

For PEN DOWN use: G1 Z90


Command-line tool
-----------------

    makeblock --help

Display usage information and available options.

    makeblock run   SCRIPT

Run the given G code script. By default, exits on the first error unless
`--continue` option is passed.

    makeblock exec  COMMAND

Execute the given G code line.

    makeblock render SCRIPT OUTPUT

Render a script to an image file.

    makeblock draw SCRIPT

Draw an image on screen.


### Dependencies

On a debian-based system, you can install the script dependencies using:

    sudo apt-get install arduino imagemagick libdevice-serialport-perl libmethod-signatures-simple-perl libmoose-perl libmoosex-strictconstructor-perl libpath-class-perl
