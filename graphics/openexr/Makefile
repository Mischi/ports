# $OpenBSD: Makefile,v 1.29 2017/07/26 22:45:24 sthen Exp $

COMMENT-main=	high dynamic range image format
COMMENT-tools=	image viewing tools for OpenEXR
COMMENT-doc=	developer documentation for OpenEXR

V=		2.2.0
REVISION=	1
DISTNAME=	openexr-$V
PKGNAME-main=	OpenEXR-$V
PKGNAME-tools=  OpenEXR-tools-$V
PKGNAME-doc=	OpenEXR-doc-$V

SHARED_LIBS +=	IlmImf               5.0      # 22.0
SHARED_LIBS +=	IlmImfUtil           0.0      # 22.0

CATEGORIES=	graphics

HOMEPAGE=	http://www.openexr.com/

# Modified BSD license
# `name of ILM not to be used for advertizing without written agreement'
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		${MASTER_SITE_SAVANNAH:=openexr/}

MULTI_PACKAGES= 	-main -tools -doc

WANTLIB-main=		m z ${COMPILER_LIBCXX} Half Iex IexMath Imath IlmThread pthread
LIB_DEPENDS-main=	graphics/ilmbase

WANTLIB-tools=		${WANTLIB-main} c m pthread ${COMPILER_LIBCXX} IlmImf>=4
LIB_DEPENDS-tools=	${LIB_DEPENDS-main} graphics/openexr
PKG_ARCH-doc=		*

# Test unhappy with separate build
#SEPARATE_BUILD=	Yes

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS+=	--disable-namespaceversioning

DOCDIR= 		${PREFIX}/share/doc/OpenEXR
FAKE_FLAGS+=		docdir=${DOCDIR}

post-install:
	${INSTALL_DATA} ${WRKSRC}/doc/*.pdf ${DOCDIR}

.include <bsd.port.mk>
