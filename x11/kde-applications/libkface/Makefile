# $OpenBSD: Makefile,v 1.3 2017/07/27 10:15:29 sthen Exp $

COMMENT =		face detection library for KDE
DISTNAME =		libkface-${VERSION}
REVISION =		0

SHARED_LIBS =		kface		0.1

CATEGORIES =		graphics math
HOMEPAGE =		https://projects.kde.org/projects/kde/kdegraphics/libs/libkface

WANTLIB =  m pthread
WANTLIB += ${COMPILER_LIBCXX}
WANTLIB += QtDBus QtGui QtSql QtSvg QtXml
WANTLIB += ${KDE4LIB}/kdeui
WANTLIB += opencv_calib3d opencv_contrib opencv_core opencv_features2d
WANTLIB += opencv_flann opencv_gpu opencv_highgui opencv_imgproc
WANTLIB += opencv_legacy opencv_ml opencv_nonfree opencv_objdetect
WANTLIB += opencv_ocl opencv_photo opencv_video

LIB_DEPENDS =		graphics/opencv

MODKDE4_USE =		libs

KFACE_V =		3.5.0
SUBST_VARS +=		KFACE_V

.include <bsd.port.mk>
