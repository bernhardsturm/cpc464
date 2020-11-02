# CPC464 Emulator with Raspberry Pi
If you want to build your own 1984 CPC464 Z80-8Bit-Emulator on a dedicaded machine, then follow this instructions:

## What will I get?
You will end up with e bootable CPC464 (or CPC464+ or CPC6128) machine. Turning your power switch to on, and after a few seconds (yes, it is not as quick as the original machine), you are taken back to the year 1984. 
You can use old original games on disc or tape (tape and disc drive will be emulated, too). You can even plug in an old Joystick, and game like 1984 all over again. Or you can teach your kids (or yourself) good old BASIC.

## Who does it work?
The emulator runs on Raspberry Pi hardware. So all you need is a spare monitor, and a keyboard, and off you go.

## Let's Start
### The Hardware
You will need a [Raspberry Pi 4](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/?resellerType=home) as this model offers sufficient performance for our emulator. If you plan to build an fully independent system, then here is the list:

- [Raspberry Pi 4 Model B, Starter Kit](https://www.digitec.ch/de/s1/product/raspberry-pi-4-4g-model-b-full-starter-kit-universal-armv8-entwicklungsboard-kit-12428788)
- [AOC 22" Display](https://www.digitec.ch/de/s1/product/aoc-22b1h-22-1920-x-1080-pixels-monitor-8718229)
- [Raspberry Keyboard, German](https://www.digitec.ch/de/s1/product/raspberry-pi-rpi-kyb-de-kabel-tastatur-11322112)
- [HDMI-Cable](https://www.digitec.ch/de/s1/product/raspberry-pi-micro-hdmi-to-hdmi-1m-hdmi-video-kabel-11268477)
- [Joystick RetroBit](https://www.digitec.ch/de/s1/product/retro-bit-the-c64-joystick-gaming-controller-12504961)
- [Speaker Hama Sonic Mobil 185](https://www.digitec.ch/de/s1/product/hama-sonic-mobil-185-pc-lautsprecher-8051340)

Total cost approx: CHF 300.-

### The Software
The Raspberry Pi 4 comes with an SD card with Noobs pre-installed. We will use this system as our host platform. 
For the emulator we will use the [Caprice32 CPC Emulator from Colin Pitrat](https://github.com/ColinPitrat/caprice32). In order to use the emulator on a Raspberry Pi we have to compile it according to the manual from Colin Pitrat (it compiles on a Pi4 as well):

#### Compile the Emulator
Debug behavior and release behavior when locating configuration file
If you compile Caprice32 yourself with plain make, behavior is debug-oriented. By default at run-time it will look for cap32.cfg in the current directory of the process that launches it, not in the executable location as stated in the documentation. To get the documented behavior, use APP_PATH like in the examples below.

If you compile Caprice32 yourself with plain make, behavior is
debug-oriented.  By default at run-time it will look for `cap32.cfg`
in the *current directory of the process* that launches it, not in the
executable location as stated in the documentation.  To get the
documented behavior, use `APP_PATH` like in the examples below.

##### From Git

```
git clone https://github.com/ColinPitrat/caprice32.git
cd caprice32
make APP_PATH="$PWD"
./cap32
```

##### From releases

Download a release from https://github.com/ColinPitrat/caprice32/releases.
Decompress it and then from a terminal in the resulting directory:

```
make APP_PATH="$PWD"
./cap32
```

### The Documentation
Here you will find the complete CPC464 manual as a PDF. Print it, and bind it to a book. This will give you a very good introduction into BASIC programming:
- [CPC 464 Manual Deutsch, PDF](https://github.com/bernhardsturm/cpc464/blob/main/Schneider_Bedienungshandbuch_CPC464.pdf)
