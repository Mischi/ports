# $OpenBSD: Makefile,v 1.36 2017/09/23 10:51:07 sthen Exp $

COMMENT=		represent and manage a libvirt hypervisor connection

V=			1.3.5
DISTNAME=		Sys-Virt-$V
REVISION=		1
CATEGORIES=		sysutils

HOMEPAGE=		https://libvirt.org/

# perl
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c perl virt

MODULES=		cpan

MODCPAN_EXAMPLES=	Yes

LIB_DEPENDS=		sysutils/libvirt>=$V

RUN_DEPENDS=		textproc/p5-XML-XPath

MAKE_ENV+=		TEST_POD=1

.include <bsd.port.mk>
