# $OpenBSD: Makefile,v 1.5 2017/01/27 22:14:33 afresh1 Exp $

COMMENT =	most commonly needed test functions and features
DISTNAME =	Test-Most-0.35
CATEGORIES =	devel
MODULES =	cpan
PKG_ARCH =	*

MAINTAINER =	Andrew Fresh <afresh1@openbsd.org>

# perl_5
PERMIT_PACKAGE_CDROM =	Yes

RUN_DEPENDS =	devel/p5-Exception-Class>=1.14 \
		devel/p5-Test-Deep>=0.119 \
		devel/p5-Test-Differences>=0.64 \
		devel/p5-Test-Exception>=0.43 \
		devel/p5-Test-Warn>=0.30

.include <bsd.port.mk>
