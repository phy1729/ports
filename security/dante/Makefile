# $OpenBSD: Makefile,v 1.49 2018/02/20 16:41:59 bket Exp $

COMMENT=	SOCKS client and server

DISTNAME=	dante-1.4.2

CATEGORIES=	security

SHARED_LIBS=	dsocks	1.3 \
		socks	1.3
MODGNU_SHARED_LIBS=dsocks	'-all-dynamic' \
		socks		''

HOMEPAGE=	https://www.inet.no/dante/

MASTER_SITES=	${HOMEPAGE}/files/

MAINTAINER=     Jakob Schlyter <jakob@openbsd.org>

# BSD/CMU
PERMIT_PACKAGE_CDROM=Yes

WANTLIB=	c m

CONFIGURE_STYLE= gnu
CONFIGURE_ARGS+= --enable-static
CONFIGURE_ARGS+= --without-gssapi \
		--without-krb5 \
		--without-ldap \
		--without-libwrap \
		--without-pam \
		--without-sasl \
		--without-upnp

pre-configure:
	${SUBST_CMD} ${WRKSRC}/bin/socksify.in

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/dante
	${INSTALL_DATA} ${WRKSRC}/doc/README.* ${PREFIX}/share/doc/dante
	${INSTALL_DATA} ${WRKSRC}/doc/SOCKS4.* ${PREFIX}/share/doc/dante
	${INSTALL_DATA} ${WRKSRC}/doc/rfc* ${PREFIX}/share/doc/dante
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/dante
	${INSTALL_DATA} ${WRKSRC}/example/*.conf ${PREFIX}/share/examples/dante

.include <bsd.port.mk>
