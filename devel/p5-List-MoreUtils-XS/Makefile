# $OpenBSD: Makefile,v 1.3 2017/10/05 14:41:06 bluhm Exp $

COMMENT =	provide compiled List::MoreUtils functions

DISTNAME =	List-MoreUtils-XS-0.426

CATEGORIES =	devel

MAINTAINER =		Alexander Bluhm <bluhm@openbsd.org>

# Perl 5, Apache 2.0, BSD
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c perl

MODULES =		cpan
BUILD_DEPENDS =		devel/p5-Config-AutoConf>=0.315 \
			sysutils/p5-Capture-Tiny
TEST_DEPENDS =		devel/p5-Test-LeakTrace \
			devel/p5-List-MoreUtils>=0.423

post-extract:
		rm -r ${WRKSRC}/inc/inc_* ${WRKSRC}/inc/latest*

.include <bsd.port.mk>
