# $OpenBSD: Makefile,v 1.4 2018/07/24 12:18:01 fcambus Exp $

COMMENT =	encoder/decoder implementation for DEC SIXEL graphics

V =		1.8.2
DISTNAME =	libsixel-$V

SHARED_LIBS +=	sixel	1.0	# 1.6

CATEGORIES =	graphics

HOMEPAGE =	https://github.com/saitoha/libsixel

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=	c jpeg m png z

MASTER_SITES =	https://github.com/saitoha/libsixel/releases/download/v$V/

LIB_DEPENDS =	graphics/jpeg \
		graphics/png

CONFIGURE_STYLE = gnu

CONFIGURE_ARGS += --disable-python \
		  --without-libcurl

# Requires Python
NO_TEST =	Yes

.include <bsd.port.mk>
