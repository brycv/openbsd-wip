# $OpenBSD: Makefile,v 1.5 2018/06/29 22:16:14 espie Exp $

# - Drop all upstreamed patches
# - Fix a piece of code that doesn't take account of OSes
#   where fileno(3) is a macro
# - Now use git submodules, drop GH_* and use the full tar.xz bundle
# XXX GLES would require a bunch of new port, i don't know if we want this.
# XXX There may be more supported archs

# =====================================================================

# Requires OpenGL>=3.3, only usable on archs that support
# modern video cards
ONLY_FOR_ARCHS =		amd64 aarch64 i386

COMMENT =		clone of the touhou games

VERSION =		v1.3
DISTNAME =		taisei-${VERSION}
PKGNAME =		taisei-${VERSION:S/^v//}

CATEGORIES =		games

HOMEPAGE =		https://taisei-project.org/

# MIT
# Soundtrack: CC-BY 4.0 / Photos: PD and CC-0
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += SDL2 SDL2_mixer c crypto freetype m png16 webpdecoder
WANTLIB += z

MASTER_SITES=	https://github.com/taisei-project/taisei/releases/download/${VERSION}/

EXTRACT_SUFX=		.tar.xz

MODULES =		devel/meson \
			lang/python

MODPY_RUNDEP =		No
MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}

RUN_DEPENDS =		devel/desktop-file-utils \
			misc/shared-mime-info \
			x11/gtk+3,-guic

LIB_DEPENDS =		devel/sdl2>=2.0.5 \
			devel/sdl2-mixer \
			graphics/libwebp>=0.5 \
			graphics/png>=1.5.0

# Don't include docs
# Don't zip the ressources, it avoids using archivers/libzip
CONFIGURE_ARGS +=	-Ddocs=false \
			-Denable_zip=false

NO_TEST =		Yes

.include <bsd.port.mk>
