if USE_MPGLIB
noinst_LTLIBRARIES = libmpglib.la
endif

INCLUDES = -I$(top_srcdir)

if USE_NEON
neon_SOURCES = dct64_neon.S synth_neon.S
neon_CFLAGS = -DUSE_NEON
else
neon_SOURCES = 
neon_CFLAGS =
endif

libmpglib_la_CFLAGS = -DLAYER1 -DLAYER2 -DLAYER3 $(neon_CFLAGS)

libmpglib_la_SOURCES =	\
	mpglib_common.c     \
	huffman.h           \
	layer1.c            \
	tabinit.c           \
	dct64_i386.c        \
	interface.c         \
	layer2.c            \
	mpg123_sdlsound.h   \
	decode_i386.c       \
	l2tables.h          \
	layer3.c            \
	mpglib_sdlsound.h   \
	$(neon_SOURCES)

EXTRA_DIST = CHANGES README README-sdlsound TODO main.c

