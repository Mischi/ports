# $OpenBSD: Makefile,v 1.5 2016/03/20 19:57:05 naddy Exp $

COMMENT =	driver to format LaTeX documents

DISTNAME =	LaTeX-Driver-0.200.4
CATEGORIES =	textproc

MODULES =	cpan
PKG_ARCH =	*

MAINTAINER =	Andrew Fresh <afresh1@openbsd.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

#CONFIGURE_ENV+=		PREFIX=${PREFIX}

RUN_DEPENDS =	print/texlive/base \
		devel/p5-Class-Accessor>=0 \
		devel/p5-Exception-Class>=0 \
		devel/p5-File-Slurp>=0 \
		devel/p5-File-pushd>=0 \
		devel/p5-Readonly>=0

TEST_DEPENDS=          print/texlive/texmf,-full

post-install:
	rm -f ${PREFIX}/${P5SITE}/LaTeX/Driver.pm.new

.include <bsd.port.mk>
