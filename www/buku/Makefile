# $OpenBSD: Makefile,v 1.4 2017/11/11 08:21:34 feinerer Exp $

COMMENT =	powerful command-line bookmark manager

MODPY_EGG_VERSION =	3.5
DISTNAME =	buku-${MODPY_EGG_VERSION}

CATEGORIES =	www

MAINTAINER =		Ingo Feinerer <feinerer@logic.at>

# GPLv3+
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python
MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}
MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes
RUN_DEPENDS =		security/py-cryptography${MODPY_FLAVOR} \
			www/py-beautifulsoup4${MODPY_FLAVOR} \
			www/py-requests${MODPY_FLAVOR} \
			www/py-urllib3${MODPY_FLAVOR}

post-install:
	${INSTALL_MAN} ${WRKSRC}/buku.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
