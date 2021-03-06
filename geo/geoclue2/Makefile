# $OpenBSD: Makefile,v 1.34 2017/05/29 14:43:53 jasper Exp $

COMMENT=		modular geoinformation service on top of D-Bus

VERSION=		2.4.7
DISTNAME=		geoclue-${VERSION}
PKGNAME=		geoclue2-${VERSION}
CATEGORIES=		geo devel

SHARED_LIBS +=  geoclue-2                 0.1 # 0.0

HOMEPAGE=		http://geoclue.freedesktop.org/

MAINTAINER=		Jasper Lievisse Adriaanse <jasper@openbsd.org>, \
			Antoine Jacoutot <ajacoutot@openbsd.org>

# LGPLv2
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		http://freedesktop.org/software/geoclue/releases/${VERSION:R}/
EXTRACT_SUFX=		.tar.xz

WANTLIB += c ffi gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 json-glib-1.0
WANTLIB += lzma m pcre pthread soup-2.4 sqlite3 xml2 z iconv intl
WANTLIB += avahi-client avahi-common avahi-glib dbus-1

MODULES=		textproc/intltool \
			x11/gnome

LIB_DEPENDS=		devel/libsoup \
			devel/json-glib \
			net/avahi

# XXX requires DBus support in wpa_supplicant
# (wpa_supplicant in OpenBSD is also crippled in other ways)
#RUN_DEPENDS=		security/wpa_supplicant

# /usr/local/share/dbus-1/system-services/
RUN_DEPENDS +=		x11/dbus,-suid

MODGNOME_TOOLS=		desktop-file-utils gobject-introspection

USE_GMAKE=		Yes

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS=		--with-dbus-service-user=_geoclue

# disable all components requiring ModemManager
CONFIGURE_ARGS +=	--disable-3g-source \
			--disable-modem-gps-source \
			--disable-cdma-source

FAKE_FLAGS=		DBUS_SYS_DIR=${PREFIX}/share/examples/geoclue/dbus-1/system.d \
			sysconfdir=${PREFIX}/share/examples/geoclue/

# don't install the demo agent .desktop file (agent requires MM)
FAKE_FLAGS +=		apps_DATA=geoclue-where-am-i.desktop

.include <bsd.port.mk>
