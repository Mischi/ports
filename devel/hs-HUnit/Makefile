# $OpenBSD: Makefile,v 1.23 2017/11/07 21:02:18 kili Exp $

COMMENT =		unit testing framework for Haskell

# Dependency of meta/haskell-platform.
# Please do *not* update without thinking.
PORTROACH =		ignore:1

DISTNAME =		HUnit-1.3.1.1
CATEGORIES =		devel
HOMEPAGE =		http://hunit.sourceforge.net/

MAINTAINER =		Matthias Kilian <kili@openbsd.org>

# BSD3
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ghc

MODGHC_BUILD =		cabal hackage haddock register

MODGHC_PACKAGE_KEY =	21JuQs5D85SLjuJsLVrBpA

.include <bsd.port.mk>
