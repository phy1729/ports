# $OpenBSD: Makefile,v 1.122 2018/08/13 13:31:39 solene Exp $

COMMENT=	library for manipulating PNG images

VERSION=	1.6.35
DISTNAME=	libpng-${VERSION}
PKGNAME=	png-${VERSION}
CATEGORIES=	graphics
DPB_PROPERTIES=	parallel
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=libpng/}
EXTRACT_SUFX=	.tar.xz

SHARED_LIBS=	png16	17.5 \
		png	17.5

HOMEPAGE=	http://www.libpng.org/pub/png/libpng.html

# BSD
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c m z

SEPARATE_BUILD=	Yes
CONFIGURE_STYLE=gnu

post-install:
	cd ${PREFIX}/lib; \
	    ln -s libpng16.so.${LIBpng16_VERSION} libpng.so.${LIBpng_VERSION}; \
	    rm libpng.la; cp -p libpng16.la libpng.la; \
	    sed -i 's/libpng16/libpng/g' libpng.la

.include <bsd.port.mk>
