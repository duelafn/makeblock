

This uses the undocumented feature of Arduino - pins 14-19 correspond to analog 0-5


// === Pinout:
// The pinout table below is correct except that it documents the DIP package,
// but the Makeblock Orion uses the QFP package. The table is based on
// 'Arduino - PinMapping168.pdf' which can be downloaded from arduino.cc.

// When this document says "digital pin n", that is simply "n" in the *.ino
// firmware source and the table.  By extension, "analog input m" is "Am" in
// the firmware and the table.  Pins 14-19 correspond to analog 0-5,
// and those number are also shown in the table.

// The first four columns below summarize the ATmega 168/328 based on
// the above Arduino document.  Additional columns are based on
// MakeblockOrion.pdf.

// "m-n" notation indicates the Orion RJ25 jack number "m" pin "n".
// Using Makeblock_Orion_Schematic_V1.0.pdf as a guide,  SDA and SCL refer to
// pins A4/A5 (present on most RJ25s as pins 2/1), which can be used for I2C.

// RJ25 #5 is the serial port and shares signals with the on-board CH340G,
// which adapts USB to serial.

// There is also a TB6612 stepper motor driver, but it looks like
// we're not using it in the X/Y plotter.  It can be used to drive
// motors connected to P3 and P4.  It also drives bicolor blue/green
// LEDs, which would be cool to play with.  It's not clear how much
// current is appropriate for these LEDs, but the inline resister
// is 10K.  (Compare this to 2.2K on the other on-board LEDs, which
// operate at ~2mA.)  The TB6612 datasheet specifies 4.5 < V-M < 13.5,
// with 5V as typical.  P2 seems to be the V-M supply volatage,
// but I should put a volt meter to it and make sure it isn't
// beingg supplies somewhere else.

//  DIP QFP     Fun     Arduino     RJ25    Orion
//   1  29      PC6     reset
//   2  30      PD0     0/RX        5-6     CH340G/RX/LEN (red)
//   3  31      PD1     1/TX        5-5     CH340G/TX/LED (red)
//   4  32      PD2     2           4-6
//   5   1      PD3     3/PWM       2-5
//   6   2      PD4     4                   TB6612/BIN/P4/LED (direction/color/blue-green)
//   7   4/6    VCC     VCC
//   8   3/5    GND     GND
//   9   7      PB6     XTAL
//  10   8      PB7     XTAL
//  11   9      PD5     5/PWM               TB6612/PWMB/P4/LED
//  12  10      PD6     6/PWM               TB6612/PWMA/P3/LED
//  13  11      PD7     7                   TB6612/AIN/P3/LED (direction/color/blue-green)
//  14  12      PB0     8           4-5
//  15  13      PB1     9/PWM       2-6
//  16  14      PB2     10/PWM      1-6
//  17  15      PB3     11/PWM      1-5
//  18  16      PB4     12          3-5
//  19  17      PB5     13/LED      3-6     LED (blue)
//  20  18      AVCC    VCC
//  21  20      AREF    AREF
//  22  21      GND     GND
//  23  23      PC0     14/A0       8-6
//  24  24      PC1     15/A1       7-6
//  25  25      PC2     16/A2       6-5
//  26  26      PC3     17/A3       6-6
//  27  27      PC4/SDA 18/A4       x-2     TWI/I2C/SDA
//  28  28      PC5/SCL 19/A5       x-1     TWI/I2C/SCL
//  n/a 19      ADC6    A6          7-6
//  n/a 22      ADC7    A7          8-5
//  n/a n/a             n/a         5-1     CH340G/DTR
//  n/a n/a             n/a         1-3     TB6612/V-M/Motor Voltage
//  n/a n/a             n/a         2-3     TB6612/V-M/Motor Voltage
