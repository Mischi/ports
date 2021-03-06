# $OpenBSD: Makefile,v 1.11 2017/07/26 22:45:22 sthen Exp $

ONLY_FOR_ARCHS =	amd64 i386

COMMENT =		role playing game

V =			0.5.8
DISTNAME =		sumwars-${V}-src
PKGNAME =		sumwars-${V}
REVISION =		3

SUBST_VARS +=		V

CATEGORIES =		games

HOMEPAGE =		http://sumwars.org/wiki/Main_Page

MAINTAINER =		Pascal Stumpf <pascal@stumpf.co>

# GPLv3+ / CC-by-sa 3.0 for data
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += CEGUIBase-0 CEGUIOgreRenderer-0 OIS OgreMain OgreRTShaderSystem
WANTLIB += OgreTerrain X11 Xrandr alut boost_chrono-mt boost_date_time-mt
WANTLIB += boost_filesystem-mt boost_system-mt boost_thread-mt
WANTLIB += c enet m ogg openal physfs pthread tinyxml vorbis
WANTLIB += vorbisfile boost_atomic-mt ${MODLUA_WANTLIB} ${COMPILER_LIBCXX}

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=sumwars/}
EXTRACT_SUFX =		.tar.bz2

MODULES =		devel/cmake \
			devel/gettext \
			lang/lua
MODLUA_VERSION =	5.2

COMPILER =		gcc
LIB_DEPENDS =		x11/cegui \
			audio/freealut \
			audio/libvorbis \
			devel/physfs \
			devel/ois \
			net/enet

CONFIGURE_ARGS += \
	-DCMAKE_EXE_LINKER_FLAGS="-L${LOCALBASE}/lib -liconv -lintl" \
	-DSUMWARS_NO_ENET=ON \
	-DSUMWARS_NO_TINYXML=ON

NO_TEST =		Yes

WRKDIST =		${WRKDIR}/sumwars-${V}

CXXFLAGS +=		-pthread

.include <bsd.port.mk>
