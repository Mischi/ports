# $OpenBSD: Makefile,v 1.37 2017/07/26 22:45:16 sthen Exp $

COMMENT=	record and analyze your meals for nutrient composition

V=		20.1
REVISION=	1
DISTNAME=	nut-${V}
PKGNAME=	nutdb-${V}
CATEGORIES=	biology
HOMEPAGE=	http://nut.sourceforge.net/

# GPLv2+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += X11 Xau Xcursor Xdmcp Xext Xfixes Xft Xpm Xinerama
WANTLIB += c fltk fontconfig m pthread ${COMPILER_LIBCXX}

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=nut/}

NO_TEST=	Yes

LIB_DEPENDS=	x11/fltk

MAKE_FLAGS+=	CC="${CC}" \
		CXX="${CXX}" \
		OPT="" \
		prefix=${PREFIX} \
		libdir=${PREFIX}/lib/nutdb

USE_GMAKE=	Yes

pre-configure:
	perl -pi -e 's,\b(?:nut)\b,nutdb,g;s,\b(?:NUT)\b,NUTDB,g' ${WRKSRC}/nut.1

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/nut ${PREFIX}/bin/nutdb
	${INSTALL_PROGRAM} ${WRKSRC}/fltk/Nut ${PREFIX}/bin/Nutdb
	${INSTALL_MAN} ${WRKSRC}/nut.1 ${PREFIX}/man/man1/nutdb.1
	${INSTALL_DATA_DIR} ${PREFIX}/lib/nutdb
	${INSTALL_DATA} ${WRKSRC}/raw.data/* ${PREFIX}/lib/nutdb

.include <bsd.port.mk>
