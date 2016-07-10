if SDL2
lib_LTLIBRARIES = libSDL2_sound.la
else
lib_LTLIBRARIES = libSDL_sound.la
endif

if SDL2
else
SUBDIRS = decoders . playsound
endif

if SDL2
libSDL2_soundincludedir = $(includedir)/SDL
libSDL2_soundinclude_HEADERS =	\
	SDL_sound.h

libSDL2_sound_la_SOURCES =	\
	SDL_sound.c	\
	SDL_sound_internal.h	\
    alt_audio_convert.c   \
    alt_audio_convert.h  \
    audio_convert.c   \
	extra_rwops.c	\
	extra_rwops.h
else
libSDL_soundincludedir = $(includedir)/SDL
libSDL_soundinclude_HEADERS =	\
	SDL_sound.h

libSDL_sound_la_SOURCES =	\
	SDL_sound.c	\
	SDL_sound_internal.h	\
    alt_audio_convert.c   \
    alt_audio_convert.h  \
    audio_convert.c   \
	extra_rwops.c	\
	extra_rwops.h
endif

if USE_TIMIDITY
TIMIDITY_LIB = decoders/timidity/libtimidity.la
else
TIMIDITY_LIB =
endif

if USE_MPGLIB
MPGLIB_LIB = decoders/mpglib/libmpglib.la
else
MPGLIB_LIB =
endif

if SDL2
libSDL2_sound_la_LDFLAGS = 		\
	-release $(LT_RELEASE)	\
	-version-info $(LT_CURRENT):$(LT_REVISION):$(LT_AGE)
libSDL2_sound_la_LIBADD =	\
	decoders/libdecoders.la	\
	$(TIMIDITY_LIB) $(MPGLIB_LIB)
else
libSDL_sound_la_LDFLAGS = 		\
	-release $(LT_RELEASE)	\
	-version-info $(LT_CURRENT):$(LT_REVISION):$(LT_AGE)
libSDL_sound_la_LIBADD =	\
	decoders/libdecoders.la	\
	$(TIMIDITY_LIB) $(MPGLIB_LIB)
endif

EXTRA_DIST =	\
	CREDITS \
	COPYING \
	CHANGELOG \
	CWProject.sit \
	PBProjects.tar.gz \
	borland.zip \
	Doxyfile \
    VisualC

dist-hook:
	mkdir $(distdir)/docs
	echo "Docs are generated with the program "Doxygen" (http://www.doxygen.org/)," >> $(distdir)/docs/README
	echo " or can be read online at http://icculus.org/SDL_sound/docs/" >> $(distdir)/docs/README
	echo >> $(distdir)/docs/README
	rm -rf `find $(distdir) -type d -name ".svn"`

pkgconfigdir = $(libdir)/pkgconfig
if SDL2
pkgconfig_DATA = SDL2_sound.pc
else
pkgconfig_DATA = SDL_sound.pc
endif