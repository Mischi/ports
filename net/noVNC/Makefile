# $OpenBSD: Makefile,v 1.3 2016/03/16 11:49:07 sthen Exp $

COMMENT=	VNC client using HTML5 (Web Sockets, Canvas)

DISTNAME=	noVNC-20160209
GH_ACCOUNT=	kelleyk
GH_PROJECT=	noVNC
GH_COMMIT=	9ade40e815b15c7dcf732e24f6870cd0d88547c2

CATEGORIES=	net www

HOMEPAGE=	http://novnc.com/

MAINTAINER=	Stuart Henderson <sthen@openbsd.org>

# core: MPL 2.0
# (plus some others for included files)
PERMIT_PACKAGE_CDROM=	Yes

RUN_DEPENDS=	net/websockify

NO_BUILD=	Yes
NO_TEST=	Yes
PREFIX=		/var/www

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/noVNC
	cd ${WRKSRC} && pax -rw * ${PREFIX}/noVNC
	chown -R ${SHAREOWN}:${SHAREGRP} ${PREFIX}/noVNC
	chmod a=rX,u+w ${PREFIX}/noVNC
	find ${PREFIX}/noVNC -name '*.orig' -exec rm {} +
	ln -s ${TRUEPREFIX}/noVNC/utils/launch.sh \
		${WRKINST}${LOCALBASE}/bin/noVNC

# LOCALBASE isn't really correct here, but it's not as bad as
# hardcoding /usr/local.

.include <bsd.port.mk>
