# $OpenBSD: Makefile,v 1.16 2018/01/11 19:27:11 rpe Exp $

COMMENT=	proxy/masquerading daemon for the SIP protocol

DISTNAME=	siproxd-0.8.2
CATEGORIES=	telephony net
REVISION=	0

HOMEPAGE=	http://siproxd.sourceforge.net/

MAINTAINER=	Lawrence Teo <lteo@openbsd.org>

# GPLv2+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c osip2 osipparser2 pthread ltdl

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=siproxd/}

USE_LIBTOOL=	gnu
LIBTOOL_FLAGS=	--tag=disable-static

CONFIGURE_STYLE=gnu
CONFIGURE_ENV+=	LDFLAGS="-L${PREFIX}/lib"

LIB_DEPENDS=	telephony/libosip2 \
		devel/libtool,-ltdl

DOCDIR=		${PREFIX}/share/doc/siproxd
EXDIR=		${PREFIX}/share/examples/siproxd
SUBST_VARS=	PREFIX

pre-build:
	${SUBST_CMD} ${WRKSRC}/doc/siproxd.conf.example

post-install:
	${INSTALL_DATA_DIR} ${DOCDIR}
	${INSTALL_DATA} ${WRKDIST}/doc/FAQ ${DOCDIR}
	${INSTALL_DATA} ${WRKDIST}/doc/KNOWN_BUGS ${DOCDIR}
	${INSTALL_DATA_DIR} ${EXDIR}
	${INSTALL_DATA} ${WRKDIST}/doc/siproxd.conf.example ${EXDIR}
	${INSTALL_DATA} ${WRKDIST}/doc/siproxd_passwd.cfg ${EXDIR}
	rm ${PREFIX}/lib/siproxd/plugin_*.la

.include <bsd.port.mk>
