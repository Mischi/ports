# $OpenBSD: Makefile,v 1.1.1.1 2017/10/23 14:43:38 rsadowski Exp $

COMMENT =		C++ toolkit for machine learning and data analysis

DISTNAME =		dlib-19.7

SHARED_LIBS +=  dlib                      0.0 # 19.7

CATEGORIES =		devel

HOMEPAGE =		http://dlib.net/

MAINTAINER =		Rafael Sadowski <rsadowski@openbsd.org>

# MIT-like (Boost)
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} ICE SM X11 Xext gif jpeg m png sqlite3
WANTLIB += z

MASTER_SITES =		http://dlib.net/files/
EXTRACT_SUFX =		.tar.bz2

MODULES =		devel/cmake

COMPILER =		base-clang ports-clang ports-gcc

LIB_DEPENDS =		graphics/jpeg \
			graphics/png \
			graphics/giflib \
			databases/sqlite3

# XXX Disable searching for blas (cblas lacks)
# Check after math/blas update or OpenBLAS import
CONFIGURE_ARGS =	-DDLIB_USE_BLAS:Bool=OFF \
			-DDLIB_USE_LAPACK:Bool=OFF \
			-DDLIB_USE_MKL_FFT:Bool=OFF

TEST_DEPENDS =		${FULLPKGNAME}:${BUILD_PKGPATH}

pre-test:
	test -d ${WRKBUILD}/dlib/test || mkdir ${WRKBUILD}/dlib/test \
	&& cd ${WRKBUILD}/dlib/test && \
	${SETENV} CC="${CC}" CFLAGS="${CFLAGS}" \
	CXX="${CXX}" CXXFLAGS="${CXXFLAGS}" \
	${CONFIGURE_ENV} ${LOCALBASE}/bin/cmake \
	-DCMAKE_SKIP_INSTALL_ALL_DEPENDENCY:Bool=True \
		-G ${_MODCMAKE_GEN} ${CONFIGURE_ARGS} ${WRKSRC}/dlib/test
	cd ${WRKBUILD}/dlib/test && exec ${SETENV} ${MAKE_ENV} \
	${NINJA} ${NINJA_FLAGS} ${ALL_TARGET}

do-test:
	cd ${WRKBUILD}/dlib/test && ./dtest --runall


.include <bsd.port.mk>
