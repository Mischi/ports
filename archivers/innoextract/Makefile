# $OpenBSD: Makefile,v 1.7 2017/07/26 22:45:14 sthen Exp $

COMMENT=	unpack Inno Setup installers

DISTNAME=	innoextract-1.6
REVISION=	0

CATEGORIES=	archivers
HOMEPAGE=	https://constexpr.org/innoextract/

MASTER_SITES=	${HOMEPAGE}files/

MAINTAINER=	Donovan Watteau <tsoomi@gmail.com>

# zlib/libpng
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	boost_filesystem-mt boost_iostreams-mt boost_program_options-mt
WANTLIB+=	boost_system-mt c iconv lzma m pthread ${COMPILER_LIBCXX}

LIB_DEPENDS=	archivers/xz \
		converters/libiconv \
		devel/boost>=1.53.0p6

RUN_DEPENDS=	archivers/unrar

MODULES=	devel/cmake

SEPARATE_BUILD=	Yes

CXXFLAGS+=	-Wno-system-headers
CONFIGURE_ARGS+=-DCMAKE_INSTALL_PREFIX="${PREFIX}" \
		-DCMAKE_INSTALL_MANDIR="man" \
		-DDOXYGEN_EXECUTABLE="false"

NO_TEST=	Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/innoextract ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/doc/innoextract.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
