# $OpenBSD: Makefile,v 1.20 2017/07/29 20:44:35 bluhm Exp $

COMMENT =	handy web browsing in a Perl object

DISTNAME =	WWW-Mechanize-1.86

CATEGORIES =	www

MAINTAINER =		Alexander Bluhm <bluhm@openbsd.org>

# Perl_5
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		cpan
RUN_DEPENDS =		www/p5-HTML-Form>=1.00 \
			www/p5-HTML-Parser \
			www/p5-HTML-Tree \
			www/p5-LWP-Protocol-https>=6 \
			www/p5-URI \
			www/p5-libwww>=5.827 \
			www/p5-HTTP-Cookies \
			www/p5-HTTP-Message>=1.30
TEST_DEPENDS =		devel/p5-Test-Deep \
			devel/p5-Test-Exception \
			devel/p5-Test-Fatal \
			devel/p5-Test-Memory-Cycle \
			devel/p5-Test-NoWarnings \
			devel/p5-Test-Output \
			devel/p5-Test-RequiresInternet \
			devel/p5-Test-Taint \
			devel/p5-Test-Warn \
			devel/p5-Test-Warnings \
			www/p5-CGI>=4.08 \
			www/p5-HTTP-Daemon \
			www/p5-HTTP-Message \
			www/p5-HTTP-Server-Simple

PKG_ARCH =		*

.include <bsd.port.mk>
