# $OpenBSD: Makefile,v 1.41 2017/07/26 22:45:18 sthen Exp $

COMMENT=	SDL C++ GUI widget library

DISTNAME=	GUIlib-1.2.1
PKGNAME=	${DISTNAME:L}
REVISION=	2

SHARED_LIBS +=	GUI                  2.0      # .0.1

CATEGORIES=	devel graphics
MASTER_SITES=	${HOMEPAGE}/src/

HOMEPAGE=	http://www.libsdl.org/projects/GUIlib/

# Public Domain
PERMIT_PACKAGE_CDROM=   Yes

WANTLIB += SDL iconv m pthread sndio ${COMPILER_LIBCXX} usbhid

LIB_DEPENDS=	converters/libiconv \
		devel/sdl

SEPARATE_BUILD=		Yes
CONFIGURE_STYLE=	gnu
CONFIGURE_ENV+=		LDFLAGS="-L${X11BASE}/lib"

MAKE_FLAGS+=	libGUI_la_LIBADD=-lsupc++

.include <bsd.port.mk>
