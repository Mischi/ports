# $OpenBSD: Makefile,v 1.16 2017/07/26 22:45:24 sthen Exp $

COMMENT=	visualize and manipulate mathematical models

DISTNAME=	k3dsurf-0.6.2
REVISION =	6
CATEGORIES=	graphics math

HOMEPAGE=	http://k3dsurf.sourceforge.net/

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=k3dsurf/}

WANTLIB=	GL GLU X11 Xext Xmu c m pthread ${COMPILER_LIBCXX}

MODULES=	x11/qt3 devel/qmake
NO_TEST=	Yes

PORTHOME=	${WRKDIR}

# fix to avoid gcc generating a huge uncompilable intermediate assembly
.if ${MACHINE_ARCH} == "hppa"
CXXFLAGS +=             -O0
.endif

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/pixmaps
	${INSTALL_DATA} ${WRKSRC}/icon/catenoid_mini_64x64.png \
		${PREFIX}/share/pixmaps/k3dsurf.png
	${INSTALL_PROGRAM} ${WRKBUILD}/bin/k3dsurf ${PREFIX}/bin

.include <bsd.port.mk>
