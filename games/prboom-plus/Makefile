# $OpenBSD: Makefile,v 1.3 2017/09/28 22:40:01 naddy Exp $

COMMENT = 	enhanced version the PrBoom Doom engine
DISTNAME =	prboom-plus-2.5.1.3
REVISION =	1
CATEGORIES =	games x11

HOMEPAGE =	http://prboom-plus.sourceforge.net/

MAINTAINER =	Ryan Freeman <ryan@slipgate.org>

# GPLv2+
PERMIT_PACKAGE_CDROM = Yes

BUILD_DEPENDS =	archivers/unzip \
		${MODGNU_AUTOCONF_DEPENDS} \
		${MODGNU_AUTOMAKE_DEPENDS}

WANTLIB += SDL c m pthread GL GLU SDL_mixer SDL_net

LIB_DEPENDS =	devel/sdl-mixer \
		devel/sdl-net

MASTER_SITES =	${MASTER_SITE_SOURCEFORGE:=prboom-plus/}

CONFIGURE_STYLE =	gnu
AUTOCONF_VERSION =	2.65
AUTOMAKE_VERSION =	1.9
CONFIGURE_ARGS +=	--disable-cpu-opt \
			--with-waddir=${TRUEPREFIX}/share/doom
CONFIGURE_ENV +=	CPPFLAGS="${CPPFLAGS} -I${X11BASE}/include"
MODGNU_CONFIG_GUESS_DIRS=${WRKSRC}/autotools

FAKE_FLAGS +=	gamesdir=${PREFIX}/bin \
		docdir=${PREFIX}/share/doc/prboom-plus

post-extract:
	@perl -MExtUtils::Command -e dos2unix ${WRKSRC}/*

pre-configure:
	@cd ${WRKSRC} && \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} \
		AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		sh bootstrap && chmod 0755 ./configure

.include <bsd.port.mk>
