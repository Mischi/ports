# $OpenBSD: Makefile,v 1.13 2017/07/27 11:57:50 sthen Exp $

COMMENT =	KDE exiv2 wrapper
CATEGORIES =	graphics devel
DISTNAME =	libkexiv2-${MODKDE4_VERSION}
PKGSPEC =	libkexiv2-${MODKDE4_SPEC}
REVISION =	1

SHARED_LIBS =	kexiv2			51.0	# 10.0

WANTLIB =  m pthread
WANTLIB += ${COMPILER_LIBCXX}
WANTLIB += lib/qt4/QtDBus lib/qt4/QtGui lib/qt4/QtSvg lib/qt4/QtXml
WANTLIB += ${KDE4LIB}/kdeui
WANTLIB += exiv2

MODKDE4_USE =	libs

LIB_DEPENDS = 	graphics/exiv2>=0.22

post-extract:
	cp ${FILESDIR}/Kexiv2Config.cmake.in ${WRKDIST}/

.include <bsd.port.mk>
