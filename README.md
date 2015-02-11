# fuse-libretro

**fuse-libretro** is an *work in progress* port of the [Fuse Unix Spectrum Emulator](http://fuse-emulator.sourceforge.net/) to [libretro](http://www.libretro.com/). It's being developed on Windows with MinGW (32 bits) and tested on RetroArch 1.0.0.3-beta frontend, but it's known to compile and run on
Linux x86/x64 and ARM. **fuse-libretro** has been tested with some [Lakka](http://www.lakka.tv/) builds.

## Games

There are hundreds of free, legally available ZX Spectrum games at [World of Spectrum](http://www.worldofspectrum.org/). You should start at the [Visitor Voted Top 100 Best Games](http://www.worldofspectrum.org/bestgames.html).

## Emulated Machines

The only emulated machine for now is the ZX Spectrum 48K. The port correctly loads and runs ~~some~~ many games I have around.

## Core Options

The core options available on the frontend are:

* Hide video border (enabled|disabled): Hides the video border, making the game occupy the entire screen area
* Tape Fast Load (enabled|disabled): Instantly loads tape files if enabled, or disabled it to see the moving horizontal lines in the video border while the game loads
* Tape Load Sound (enabled|disabled): Outputs the tape sound if fast load is disabled
* Speaker Type (tv speaker|beeper|unfiltered): Applies an audio filter (libretro should allow for audio filters on the frontend)
* AY Stereo Separation (none|acb|abc): The AY sound chip stereo separation (whatever it is)
* Transparent Keyboard Overlay (enabled|disabled): If the keyboard overlay is transparent or opaque
* Time to Release Key in ms (100|300|500|1000): How much time to keep a key pressed before releasing it (used when a key is pressed using the keyboard overlay)

## Controllers

There are seven types of joysticks emulated:

1. Cursor
2. Kempston
3. Sinclair 1
4. Sinclair 2
5. Timex 1
6. Timex 2
7. Fuller Joystick

Users can configure their joystick types in the input configuration on the front end. However, **fuse-libretro** allows for two joysticks at maximum so only users one and two can actually use theirs in the emulation.

## Keyboard

Keyboard is **not** being emulated right now, but it's on my TODO list. If you need to press keys in a game (i.e. to choose the joystick type) use the keyboard overlay, which is displayed by pressing *select* on the controller. Don't play games where you have to write a lot yet, nor use this core to write a program for the ZX Spectrum.

## Supported Formats

Fuse can load a number of different file formats. For now, **fuse-libretro** only loads `tzx`, `tap`, and `z80` files. This decision is somewhat arbitrary (it depends if I can reliably identify the file type), so feel free to bug me to add other extensions. Please do so via issues here on GitHub.

## Save States

Supported.

## Setup

1. Compile **fuse-libretro** with `make -f Makefile.libretro`
1. Copy the resulting `fuse_libretro.dll` or `fuse_libretro.so` into the `cores` folder of your libretro frontend
1. Profit!

> It's *not* necessary to copy files to the `system` folder of your libretro frontend anymore! All supporting files are baked into the core.

## Versions

Versions that are being used to build and test **fuse-libretro**:

* Fuse 1.1.1
* libspectrum 1.1.1
* zlib 1.2.8
* bzip2 1.0.6

## TODO

See the open issues.

## Bugs

Many. Open issues or send pull requests.

## License

GNU GPLv3.0
