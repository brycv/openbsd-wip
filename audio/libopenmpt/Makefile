# $OpenBSD$

COMMENT =	OpenMPT based module player library and command-line player

DISTNAME =	libopenmpt-0.4.4+release.autotools
PKGNAME =	${DISTNAME:S/+release.autotools//}

SHARED_LIBS +=	openmpt	0.0	# 1.1

CATEGORIES =	audio devel

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

HOMEPAGE =	https://lib.openmpt.org/libopenmpt/

# BSD
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=	${COMPILER_LIBCXX} FLAC c m mpg123 ogg portaudio sndfile
WANTLIB +=	sndio vorbis vorbisenc vorbisfile z

MASTER_SITES =	https://lib.openmpt.org/files/libopenmpt/src/

LIB_DEPENDS =	audio/flac \
		audio/libsndfile \
		audio/libvorbis \
		audio/mpg123 \
		audio/portaudio-svn

CONFIGURE_STYLE = gnu

CONFIGURE_ARGS+= --without-portaudiocpp

.include <bsd.port.mk>
