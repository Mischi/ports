# $OpenBSD: Makefile,v 1.15 2017/01/03 19:27:52 landry Exp $

COMMENT =	python package to parse and build CSS

CATEGORIES =	textproc

MODPY_EGG_VERSION =	1.0.1
DISTNAME =	cssutils-${MODPY_EGG_VERSION}
PKGNAME =	py-${DISTNAME}
MODPY_PI =	Yes
REVISION =	0

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

HOMEPAGE =	http://cthedot.de/cssutils/

MODULES =	lang/python

MODPY_SETUPTOOLS =	Yes

FLAVORS =	python3
FLAVOR ?=

# Requires older of devel/py-pbr
NO_TEST =		Yes

post-install:
	chmod 444 ${WRKINST}/${MODPY_SITEPKG}/${DISTNAME}-py${MODPY_VERSION}.egg-info/*
.for b in csscapture csscombine cssparse
	mv -f ${PREFIX}/bin/$b ${PREFIX}/bin/$b${MODPY_BIN_SUFFIX}
.endfor

.include <bsd.port.mk>
