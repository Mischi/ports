# $OpenBSD: Makefile,v 1.3 2016/03/11 19:59:11 naddy Exp $

COMMENT=	create MusicBrainz DiscIDs from audio CDs

DISTNAME=	libdiscid-0.6.1
CATEGORIES=	audio

SHARED_LIBS +=	discid 0.0      # 0.0

MAINTAINER=	Donovan Watteau <tsoomi@gmail.com>

HOMEPAGE=	https://musicbrainz.org/doc/libdiscid/

# LGPLv2.1+
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=	http://ftp.musicbrainz.org/pub/musicbrainz/libdiscid/

SEPARATE_BUILD=	Yes

CONFIGURE_STYLE=gnu
CONFIGURE_ENV=	ac_cv_header_musicbrainz5_mb5_c_h=no

.include <bsd.port.mk>
