# $OpenBSD: Makefile,v 1.10 2017/11/07 22:25:04 kili Exp $

COMMENT =		a Haskell 98 logically uninhabited data type

DISTNAME =		void-0.7.1
CATEGORIES =		devel

MAINTAINER =		Matthias Kilian <kili@openbsd.org>

# BSD3
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ghc

MODGHC_BUILD =		cabal hackage haddock register

MODGHC_PACKAGE_KEY =	KbLCoLSS1x50ViJwRVqHCO

BUILD_DEPENDS =		${RUN_DEPENDS}

RUN_DEPENDS =		devel/hs-hashable>=1.1 \
			devel/hs-semigroups>=0.8.2

.include <bsd.port.mk>
