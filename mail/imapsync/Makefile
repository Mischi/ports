# $OpenBSD: Makefile,v 1.17 2017/05/10 12:47:56 pea Exp $

GH_ACCOUNT =    imapsync
GH_PROJECT =    imapsync

COMMENT=	IMAP synchronization tool

DISTNAME=	imapsync-1.727
CATEGORIES=	mail

MAINTAINER=	Pierre-Emmanuel Andre <pea@openbsd.org>

# NO_LIMIT
PERMIT_PACKAGE_CDROM=	Yes

WRKDIST=	${WRKDIR}/imapsync-${DISTNAME}

RUN_DEPENDS=	converters/p5-DateManip \
		security/p5-IO-Socket-SSL \
		security/p5-Digest-HMAC \
		mail/p5-Mail-IMAPClient \
		net/p5-IO-Socket-INET6 \
		security/p5-IO-Socket-SSL \
		devel/p5-IO-Tee \
		converters/p5-Unicode-String \
		www/p5-URI \
		security/p5-Authen-NTLM \
		devel/p5-File-Copy-Recursive \
		devel/p5-Parse-RecDescent \
		devel/p5-Test-Pod \
		devel/p5-Data-Uniqid \
		devel/p5-Readonly

NO_BUILD=	Yes
NO_TEST=	Yes
PKG_ARCH=	*

do-install:
	/usr/bin/pod2man ${WRKSRC}/imapsync ${WRKSRC}/imapsync.1
	${INSTALL_SCRIPT} ${WRKSRC}/imapsync ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/imapsync.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
