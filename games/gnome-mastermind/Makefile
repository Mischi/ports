# $OpenBSD: Makefile,v 1.28 2017/10/23 17:10:49 sthen Exp $

COMMENT =	Mastermind clone reflexion game

GNOME_PROJECT =	gnome-mastermind
GNOME_VERSION =	0.3.1
REVISION =	14

CATEGORIES =	games

HOMEPAGE =	http://www.autistici.org/gnome-mastermind/

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	http://download.gna.org/gnome-mastermind/
EXTRACT_SUFX=		.tar.bz2

MODULES =	devel/gettext \
		x11/gnome

LIB_DEPENDS =	x11/gtk+2 \
		devel/gconf2

MODGNOME_TOOLS += desktop-file-utils gtk-update-icon-cache yelp
CONFIGURE_STYLE =	gnu

WANTLIB += X11 Xcomposite Xcursor Xdamage Xext
WANTLIB += Xfixes Xi Xinerama Xrandr Xrender atk-1.0 c cairo dbus-1
WANTLIB += dbus-glib-1 expat fontconfig freetype gio-2.0 glib-2.0
WANTLIB += gmodule-2.0 gobject-2.0 gthread-2.0 m pango-1.0
WANTLIB += pangocairo-1.0 pangoft2-1.0 pcre pixman-1 png pthread
WANTLIB += xcb z gdk_pixbuf-2.0 gdk-x11-2.0>=1000
WANTLIB += gtk-x11-2.0>=1000 gconf-2>=6
WANTLIB += ffi graphite2 harfbuzz xcb-render xcb-shm

.include <bsd.port.mk>
