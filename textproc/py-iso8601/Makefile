# $OpenBSD: Makefile,v 1.5 2017/08/17 18:51:33 jasper Exp $

COMMENT =		Python module to parse ISO 8601 dates

MODPY_EGG_VERSION =	0.1.12
DISTNAME =		iso8601-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		textproc

HOMEPAGE =		https://bitbucket.org/micktwomey/pyiso8601

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MODPY_PI =		Yes

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes

FLAVORS=		python3
FLAVOR?=

do-test: fake
	cd ${WRKSRC}; LC_ALL=C \
	    PYTHONPATH=${WRKINST}${MODPY_SITEPKG} \
	    py.test${MODPY_BIN_SUFFIX} --verbose iso8601

.include <bsd.port.mk>
