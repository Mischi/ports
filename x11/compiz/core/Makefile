# $OpenBSD: Makefile,v 1.33 2017/10/23 17:11:03 sthen Exp $

COMMENT =	OpenGL window and compositing manager

V =		0.8.8
DISTNAME =	compiz-${V}
REVISION =	4

SHARED_LIBS =	decoration	1.0

# MIT, GPL and LGPL
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += GL GLU ICE SM X11 X11-xcb XRes Xau Xcomposite Xcursor Xdamage
WANTLIB += Xdmcp Xext Xfixes Xi Xinerama Xrandr Xrender Xxf86vm atk-1.0
WANTLIB += c cairo croco-0.6 dbus-1 dbus-glib-1 drm expat ffi fontconfig
WANTLIB += freetype gdk-x11-2.0 gdk_pixbuf-2.0 gio-2.0 glapi glib-2.0
WANTLIB += gmodule-2.0 gobject-2.0 graphite2 gthread-2.0 gtk-x11-2.0
WANTLIB += harfbuzz lzma m pango-1.0 pangocairo-1.0 pangoft2-1.0 pcre
WANTLIB += pixman-1 png pthread rsvg-2
WANTLIB += startup-notification-1 ${COMPILER_LIBCXX} wnck-1 xcb xcb-dri2 xcb-glx
WANTLIB += xcb-render xcb-shm xcb-util xml2 xslt z

MASTER_SITES =	http://releases.compiz.org/${V}/

MODULES =	devel/gconf2 \
		devel/gettext \
		textproc/intltool

MODGCONF2_SCHEMAS_DIR =	compiz

LIB_DEPENDS =	devel/startup-notification \
		devel/libwnck \
		textproc/libxml \
		textproc/libxslt \
		x11/gnome/librsvg \
		x11/gtk+2

USE_GMAKE =	Yes

LIBTOOL_FLAGS =	--tag=disable-static

CONFIGURE_STYLE	= gnu
CONFIGURE_ARGS = --disable-static \
		 --disable-fuse \
		 --disable-inotify \
		 --disable-metacity \
		 --disable-gnome \
		 --disable-gnome-keybindings \
		 --disable-kde \
		 --disable-kde4 \
		 --disable-kconfig
CONFIGURE_ENV =	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib"

post-install:
	@rm -f ${PREFIX}/lib/compiz/*.la

.include <bsd.port.mk>
