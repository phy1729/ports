# $OpenBSD: Makefile,v 1.9 2018/01/29 00:04:23 jca Exp $

COMMENT =		library which implements the IRC protocol
DISTNAME =		libircclient-1.9
CATEGORIES =		net
HOMEPAGE =		http://www.ulduzsoft.com/linux/libircclient/

SHARED_LIBS =		ircclient 1.0

# LGPLv2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += crypto pthread ssl

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=libircclient/}

NO_TEST =		Yes

CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS =	--enable-shared \
			--enable-openssl \
			--enable-ipv6

MAKE_FLAGS =		APIVERSION=${LIBircclient_VERSION}
FAKE_FLAGS =		exec_prefix=${PREFIX}

post-install:
	rm ${PREFIX}/lib/libircclient.so

.include <bsd.port.mk>
