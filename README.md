# EasyRPG Player

EasyRPG Player is a game interpreter to play RPG Maker 2000, 2003 and EasyRPG
games. It uses the LCF parser library (liblcf) to read RPG Maker game data.

EasyRPG Player is part of the EasyRPG Project. More information is
available at the project website: https://easyrpg.org/


## Documentation

Documentation is available at the documentation wiki: https://wiki.easyrpg.org


## Requirements

### minimal / required

- liblcf for RPG Maker data reading. https://github.com/EasyRPG/liblcf
- SDL2 for screen backend support.
- Pixman for low level pixel manipulation.
- libpng for PNG image support.
- zlib for XYZ image support.

### extended / recommended

- FreeType2 for external font support (+ HarfBuzz for Unicode text shaping)
- mpg123 for better MP3 audio support
- WildMIDI for better MIDI audio support
- Libvorbis / Tremor for Ogg Vorbis audio support
- opusfile for Opus audio support
- libsndfile for better WAVE audio support
- libxmp for better tracker music support
- SpeexDSP for proper audio resampling
- SDL2_mixer for audio mixing. Used as a fallback when none of the provided
  audio libraries support the format. Due to API limitations not all audio
  effects are possible through SDL2_mixer audio.

SDL 1.2 and SDL_mixer 1.2 are still supported, but deprecated.


## Daily builds

Up to date binaries for assorted platforms are available at our continous
integration service:

https://ci.easyrpg.org/view/Player/


## Source code

EasyRPG Player development is hosted by GitHub, project files are available
in this git repository:

https://github.com/EasyRPG/Player

Released versions are also available at our Download Archive:

https://easyrpg.org/downloads/player/


## Building

### Autotools Makefile method:

Building requirements:

- pkg-config
- GNU make

Step-by-step instructions:

    tar xf easyrpg-player-0.5.4.tar.xz # unpack the tarball
    cd easyrpg-player-0.5.4            # enter in the package directory
    ./configure                        # find libraries, set options
    make                               # compile the executable

Additional building requirements when using the source tree (git):

- autoconf >= 2.69
- automake >= 1.11.4
- libtool

To generate the "configure" script, run before following the above section:

    autoreconf -i

Read more detailed instructions at:

* https://wiki.easyrpg.org/development/compiling/player/autotools


### CMake method:

Building requirements:

- pkg-config (Not on Windows)
- CMake

Step-by-step instructions:

    tar xf easyrpg-player-0.5.4.tar.xz    # unpack the tarball
    cd easyrpg-player-0.5.4               # enter in the package directory
    cmake . -DCMAKE_BUILD_TYPE=Release    # configure project
    cmake --build .                       # compile the executable
    sudo cmake --build . --target install # install system-wide

Read more detailed instructions at:

* https://wiki.easyrpg.org/development/compiling/player/cmake

CMake is the only supported way to build liblcf for Windows. All dependencies
must be installed with [vcpkg](https://github.com/Microsoft/vcpkg).

## Running EasyRPG Player

Run the `easyrpg-player` executable from a RPG Maker 2000 or 2003 game
project folder (same place as `RPG_RT.exe`).


## Bug reporting

Available options:

* File an issue at https://github.com/EasyRPG/Player/issues
* Open a thread at https://community.easyrpg.org/
* Chat with us via IRC: #easyrpg at irc.freenode.net


## License

EasyRPG Player is free software available under the GPLv3 license. See the file
COPYING for license conditions.


### 3rd party software

EasyRPG Player makes use of the following 3rd party software:

* FMMidi YM2608 FM synthesizer emulator - Copyright (c) 2003-2006 yuno
  (Yoshio Uno), provided under the (3-clause) BSD license

* PicoJSON JSON parser/serializer - Copyright (c) 2009-2010 Cybozu Labs, Inc.
  Copyright (c) 2011-2015 Kazuho Oku, provided under the (2-clause) BSD license

* Dirent interface for Microsoft Visual Studio -
  Copyright (c) 2006-2012 Toni Ronkko, provided under the MIT license
