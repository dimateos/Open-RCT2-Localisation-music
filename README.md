# OpenRCT2-OpenMusic
This project aims to create an alternative, higher quality version of the music from RollerCoaster Tycoon 2 for use in [OpenRCT2](https://github.com/OpenRCT2/OpenRCT2).

## Chat
[![Gitter](https://img.shields.io/badge/gitter-Lobby-red.svg?style=flat-square)](https://gitter.im/OpenRCT2-OpenMusic/Lobby)

## Progress
### Fairground organ style
All of the pieces from the fairground organ style are so old that they fall under public domain.

#### Theoretical background
A fairground organ is a musical instrument that usually plays by itself. It usually contains a small/medium sized pipe organ with a few different stops, lots of percussion (xylophone, tambourine, triangle, cymbals, multiple kinds of drums) and sometimes a Glockenspiel and/or Bells.
The score is provided in form of [music rolls](https://en.wikipedia.org/wiki/Music_roll) or [book music](https://en.wikipedia.org/wiki/Book_music).

The fairground organ is limited by its instruments. As all pieces should be in the same style and sound as if they are played by the same fairground organ, all arrangements are limited to the same instruments and the same set of organ registrations (yet to be determined).

Another limitation is the lack of dynamics. Fairground organs usually don't have a swell box, so dynamics are achieved by different registrations. Therefore the LilyPond files do not contain dynamic symbols for the organ parts.

#### Status
The lists of the pieces of music in the game credits and [here](http://rct.wikia.com/wiki/Music) are unfortunately not 100% correct. If you know the name of the missing pieces, please let me know!

| File | Piece of music | Status |
| ---- | -------------- | ------ |
| css4.dat | Die Regimentskinder by Julius Fučík | Work in progress |
| css5.dat | Serenade by Jonny Heykens | Work in progress |
| css6.dat | La Belle Espagnole, Op.103 by Robert Vollstedt | TODO |
| css7.dat | Dornröschens Brautfahrt by Max Rhode | TODO |
| css8.dat | Tales from the Vienna Woods Waltz by Johann Strauss II | TODO |
| css9.dat | ? | TODO |
| css11.dat | Der Haushamer Plattler (Traditional) 00:00 - 00:52 / ? | TODO |
| css12.dat | Ma Bella Bimba | TODO |
| css13.dat | The Blond Sailor by The Andrews Sisters | TODO |
| css14.dat | Overture from Poet and Peasant by Franz von Suppé | Work in progress |
| css15.dat | Multiple waltzes by Johann Strauß II: 00:00 Morgenblätter / 01:10 Die Fledermaus - Overture / 01:23 Künstlerleben / 02:09 Wiener Blut / 03:05 The Blue Danube | Work in progress |

### Other music styles

| File | Style | Status |
| ---- | ----- | ------ |
| css34.dat | Ragtime style | Adapted the score from the Mutopia Project ([current state](https://cuervo.phoenix.uberspace.de/music/ragtime.ogg)) |

Most of the other music styles are original compositions for the game, so they can't be recreated. The others can.

## Build documentation
The music in this repository has to be built, which works similar to the process of building software.

Currently, the build output is available at [https://cuervo.phoenix.uberspace.de/openrct2-openmusic/nightly/](https://cuervo.phoenix.uberspace.de/openrct2-openmusic/nightly/).

### Build Dependencies
- [BASH](http://tiswww.case.edu/php/chet/bash/bashtop.html)
- [Ninja](https://ninja-build.org/)
- [libsmf](https://sourceforge.net/projects/libsmf/)
- [CMake](https://cmake.org/)
- [GCC](https://gcc.gnu.org/)/[Clang](http://clang.llvm.org/)
- [LilyPond](http://lilypond.org/)
- [FluidSynth](http://www.fluidsynth.org/)
- [Calf Studio Gear](http://calf-studio-gear.org/)
- [lv2file](https://github.com/jeremysalwen/lv2file)
- [SoX](http://sox.sourceforge.net/)
- [opus-tools](http://opus-codec.org/downloads/)
- Multiple SoundFonts
    - BureaFuneralChapel.sf2 (currently not available for download as it is not finished yet)
    - FluidR3_GM.sf2
    - [GeneralUser GS v1.471.sf2](http://www.schristiancollins.com/generaluser.php)
    - [Nice-Upright-Piano-sf2-JNv1.3.sf2](https://sites.google.com/site/soundfonts4u/)

### Build
First, generate `build.ninja` using the `geninja.sh` script:

    $ ./geninja.sh

Then, run `build.sh`:

    $ ./build.sh

This will build all required files into `out/` and the 'official' output to `out/release/`.

Some build properties can be modified in `musictools/config.sh`.
