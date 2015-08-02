# Arduino Library for 74597 PISO shift register

## Installation
to install, clone this repo (into a folder called shift_74597) and then copy the folder into the 'libraries' folder in your arduino installation.

## Usage
Instatiate the shift_74597 class near the top of your sketch.
Change the pin names below to the numbers of the arduino pins.
```
    shift_74597 myShifter = shift_74597(QH, SCK, RCK, SLOAD, SCLR);
```

In the arduino setup function, call the init function on the shifter instance
```
    myShifter.init();
```

Then you can get the value of a shift register like so:
```
    myShifter.load();
    char myInput = myShifter.getByte();
```

If you have chained multiple shift registers together then you can read each one in sequence after a single load() call.
```
    myShifter.load();
    char myInput0 = myShifter.getByte();
    char myInput1 = myShifter.getByte();
    char myInput2 = myShifter.getByte();
```
