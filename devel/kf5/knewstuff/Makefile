# $OpenBSD: Makefile,v 1.6 2017/10/26 07:53:23 rsadowski Exp $

COMMENT =		KDE framework for sharing additional application data
DISTNAME =		knewstuff-${VERSION}

SHARED_LIBS +=  KF5NewStuff               3.0
SHARED_LIBS +=  KF5NewStuffCore           2.0

WANTLIB += ${COMPILER_LIBCXX} KF5Archive KF5Attica KF5Auth KF5Codecs
WANTLIB += KF5Completion KF5ConfigCore KF5ConfigGui KF5ConfigWidgets
WANTLIB += KF5CoreAddons KF5I18n KF5IconThemes KF5ItemViews KF5JobWidgets
WANTLIB += KF5KIOCore KF5KIOWidgets KF5Service KF5SonnetUi KF5TextWidgets
WANTLIB += KF5WidgetsAddons KF5XmlGui Qt5Core Qt5DBus Qt5Gui Qt5Network
WANTLIB += Qt5Qml Qt5Quick Qt5Widgets Qt5Xml m

BUILD_DEPENDS =		devel/gettext-tools

LIB_DEPENDS =		devel/kf5/karchive \
			devel/kf5/attica \
			devel/kf5/kcompletion \
			devel/kf5/kconfig \
			devel/kf5/kcoreaddons \
			devel/kf5/ki18n \
			devel/kf5/kiconthemes \
			devel/kf5/kitemviews \
			devel/kf5/kio \
			devel/kf5/kservice \
			devel/kf5/ktextwidgets \
			devel/kf5/kwidgetsaddons \
			devel/kf5/kxmlgui \
			x11/qt5/qtdeclarative

PORTHOME =		${WRKDIR}
TEST_IS_INTERACTIVE =	X11

.include <bsd.port.mk>
