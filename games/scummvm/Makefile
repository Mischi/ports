# $OpenBSD: Makefile,v 1.73 2017/07/26 22:45:22 sthen Exp $

COMMENT=	graphical adventure game interpreter
V=		1.9.0
REVISION =	2
DISTNAME=	scummvm-${V}
CATEGORIES=	games x11 emulators
MASTER_SITES=	http://www.scummvm.org/frs/scummvm/${V}/

HOMEPAGE=	http://www.scummvm.org/

MAINTAINER=	Jonathan Gray <jsg@openbsd.org>

# GPLv2+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += FLAC SDL2 c faad freetype jpeg m mad png sndio ${COMPILER_LIBCXX}
WANTLIB += theoradec z

.if ${MACHINE_ARCH} == "i386"
BUILD_DEPENDS=	devel/nasm
.endif

# GCC 4.2.1 miscompiles this on at least ppc, so play safe and
# just use a newer compiler everywhere.
COMPILER=	gcc

RUN_DEPENDS=	devel/desktop-file-utils
LIB_DEPENDS=	audio/libmad \
		audio/flac \
		audio/faad>=2.7 \
		devel/sdl2 \
		graphics/png \
		graphics/jpeg \
		multimedia/libtheora

CONFIGURE_STYLE=simple
CONFIGURE_ARGS+= --disable-alsa \
		--disable-debug \
		--disable-fluidsynth \
		--disable-seq-midi \
		--disable-mpeg2 \
		--disable-sdlnet \
		--disable-libcurl \
		--enable-sndio \
		--mandir="${LOCALBASE}/man"
CONFIGURE_ENV+=	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib"

.if ${MACHINE_ARCH} == "arm"
CONFIGURE_ARGS +=	--enable-tremor --disable-vorbis
LIB_DEPENDS +=		audio/tremor
WANTLIB +=		vorbisidec>=1
.else
LIB_DEPENDS +=		audio/libvorbis
WANTLIB +=		ogg vorbis>=0 vorbisfile>=1
.endif

NO_TEST=	Yes
USE_GMAKE=	Yes

MAKE_ENV+=	CXXFLAGS="${CXXFLAGS}" CXX="${CXX}" VERBOSE_BUILD=1

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/applications
	${INSTALL_DATA} ${WRKSRC}/dists/scummvm.desktop \
	    ${PREFIX}/share/applications

.include <bsd.port.mk>
