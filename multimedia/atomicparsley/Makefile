# $OpenBSD: Makefile,v 1.11 2018/11/05 17:23:41 sthen Exp $

COMMENT=	read and set MPEG-4/3GPP metadata tags

V=		0.9.6
DISTNAME=	atomicparsley-$V
REVISION=	3
DISTFILES=	${DISTNAME}{$V}.tar.bz2
WRKDIST=	${WRKDIR}/wez-atomicparsley-da2f6e4fc120

CATEGORIES=	multimedia

HOMEPAGE=	https://bitbucket.org/wez/atomicparsley/

MAINTAINER=	Stuart Henderson <sthen@openbsd.org>

# GPLv2 "or its successor"
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c m ${COMPILER_LIBCXX} z

COMPILER =		base-clang ports-gcc base-gcc

MASTER_SITES=	https://bitbucket.org/wez/atomicparsley/get/

CONFIGURE_STYLE=  gnu
CONFIGURE_ENV=    ac_cv_func_lroundf=yes \
		  OBJCXX="${CXX}"
AUTOCONF_VERSION= 2.69
AUTOMAKE_VERSION= 1.15
BUILD_DEPENDS=	${MODGNU_AUTOCONF_DEPENDS} \
		${MODGNU_AUTOMAKE_DEPENDS}

NO_TEST=	Yes
SEPARATE_BUILD= Yes

do-gen:
	cd ${WRKSRC}; AUTOCONF_VERSION=${AUTOCONF_VERSION} \
	    AUTOMAKE_VERSION=${AUTOMAKE_VERSION} ./autogen.sh

.include <bsd.port.mk>
