# $OpenBSD: Makefile,v 1.130 2017/11/02 10:56:26 jasper Exp $

COMMENT=	archive manager utility for GNOME

GNOME_PROJECT=	file-roller
GNOME_VERSION=	3.26.2

CATEGORIES=	archivers

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += Xtst X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi
WANTLIB += Xinerama Xrandr Xrender archive atk-1.0 atk-bridge-2.0
WANTLIB += atspi bz2 c cairo cairo-gobject crypto dbus-1 epoxy
WANTLIB += expat ffi fontconfig freetype gdk-3 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 graphite2
WANTLIB += gthread-2.0 gtk-3 harfbuzz iconv intl json-glib-1.0
WANTLIB += lz4 lzma m magic notify pango-1.0 pangocairo-1.0
WANTLIB += pangoft2-1.0 pcre pixman-1 png pthread
WANTLIB += xcb xcb-render xcb-shm z gnome-autoar-0 nautilus-extension

MODULES=	devel/dconf \
		x11/gnome

RUN_DEPENDS=	archivers/gcpio \
		archivers/gtar \
		archivers/p7zip \
		archivers/unzip \
		archivers/xz \
		archivers/zip \
		sysutils/cdrtools

# "The Unarchiver" has not been ported to OpenBSD yet
RUN_DEPENDS +=	archivers/unrar

LIB_DEPENDS=	archivers/libarchive>=3.1.2 \
		devel/json-glib \
		devel/libmagic \
		devel/libnotify \
		x11/gnome/nautilus

MODGNOME_TOOLS += desktop-file-utils gtk-update-icon-cache yelp

CONFIGURE_STYLE=gnu
CONFIGURE_ENV=	CPIO=${LOCALBASE}/bin/gcpio

post-install:
	rm ${PREFIX}/lib/nautilus/extensions-3.0/*.{a,la}

.include <bsd.port.mk>
