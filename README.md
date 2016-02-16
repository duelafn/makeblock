
Arduinao GCode Parser and Command-Line Tool
===========================================

Unofficial fork of the Makeblock arduino gcode interpreter ready to run on
the msot excellent Makeblock
[XY-Plotter](http://www.makeblock.cc/xy-plotter-robot-kit/).

Additionally includes a command-line tool which can send your gcode files
to the plotter without using the Arduino serial connection, and can render
your gcode files to PostScript or other image format (using the `convert`
utility from ImageMagick - `apt-get install imagemagick` on Debian-based
systems).


This repository splits the arduino files from the full
[Makeblock repository](https://github.com/Makeblock-official/XY-Plotter-2.0)
since I had no interest in the Java GRemote tool. The exact license of the
arduino `.ino` files is a bit unclear (but at least must be compatible with
the LGPL of the arduino Servo library), there is a
[bug report](https://github.com/Makeblock-official/XY-Plotter-2.0/issues/13)
asking for upstream license clarification.
