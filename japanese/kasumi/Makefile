# $OpenBSD: Makefile,v 1.19 2017/07/26 22:45:25 sthen Exp $

COMMENT =	personal dictionary manager for anthy

DISTNAME =	kasumi-2.5
REVISION =	7

CATEGORIES =	japanese

HOMEPAGE =	https://osdn.jp/projects/kasumi/

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	${MASTER_SITE_OSDN_JP:=kasumi/41436/}

WANTLIB += X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama
WANTLIB += Xrandr Xrender anthy anthydic atk-1.0 c cairo fontconfig
WANTLIB += freetype gdk-x11-2.0 gdk_pixbuf-2.0 gio-2.0 glib-2.0
WANTLIB += gobject-2.0 gtk-x11-2.0 iconv intl m pango-1.0 pangocairo-1.0
WANTLIB += pangoft2-1.0 pthread ${COMPILER_LIBCXX} z

BUILD_DEPENDS =	devel/gettext-tools
RUN_DEPENDS =	devel/desktop-file-utils
LIB_DEPENDS =	devel/gettext \
		inputmethods/anthy \
		x11/gtk+2

CONFIGURE_STYLE =	gnu

.include <bsd.port.mk>
