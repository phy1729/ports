# $OpenBSD: Makefile,v 1.18 2019/02/08 19:07:21 jasper Exp $

REV=		1.1
VERSION=	${REV}.2.1
EPOCH=		0
REVISION=	5
SHARED_LIBS=	net	11.0
PKGSPEC=	libnet->=1.1v0,<1.2v0

WRKDIST=	${WRKDIR}/libnet
MASTER_SITES=	https://distfiles.nl/ \
		http://packetfactory.openwall.net/libnet/dist/

AUTOCONF_VERSION=	2.57
MAKE_FLAGS=	LIBnet_VERSION=${LIBnet_VERSION}
CONFIGURE_ENV=	LIBNET_CONFIG_LIBS="-L${LOCALBASE}/lib/libnet-1.1" \
		LIBNET_CONFIG_CFLAGS="-I${LOCALBASE}/include/libnet-1.1"

post-install:
	${INSTALL_SCRIPT} ${WRKSRC}/libnet-config \
		${PREFIX}/bin/libnet-config-1.1
	@ln -sf libnet-${REV}/libnet.so.${LIBnet_VERSION} \
		${PREFIX}/lib

.include <bsd.port.mk>
