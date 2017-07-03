# SDL_sound

![SDL_sound build status](https://api.travis-ci.org/ptitSeb/SDL_sound.png "SDL_sound build status")

SDL_sound. An abstract soundfile decoder.

SDL_sound is a library that handles the decoding of several popular sound file
 formats, such as .WAV and .MP3. It is meant to make the programmer's sound
 playback tasks simpler. The programmer gives SDL_sound a filename, or feeds
 it data directly from one of many sources, and then reads the decoded
 waveform data back at her leisure. If resource constraints are a concern,
 SDL_sound can process sound data in programmer-specified blocks. Alternately,
 SDL_sound can decode a whole sound file and hand back a single pointer to the
 whole waveform. SDL_sound can also handle sample rate, audio format, and
 channel conversion on-the-fly and behind-the-scenes, if the programmer
 desires.

Please check the website for the most up-to-date information about SDL_sound:
   http://icculus.org/SDL_sound/


This version of SDL_sound can be built for SDL 1.2 or SDL 2.0. It will built by default for SDL2.
You can use `./configure --enable-sdl2=no` to have SDL_sound compiled.
The SDL2 version will be called SDL2_sound (so it can live alongside regular SDL_sound).
