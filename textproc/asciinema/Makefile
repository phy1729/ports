# $OpenBSD: Makefile,v 1.5 2018/04/06 07:41:56 ajacoutot Exp $

COMMENT=		terminal session recorder

MODPY_EGG_VERSION=	2.0.1

# MODPY_PI does not work
GH_PROJECT=		asciinema
GH_ACCOUNT=		asciinema
GH_TAGNAME=		v${MODPY_EGG_VERSION}

CATEGORIES=		textproc graphics

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_SETUPTOOLS=	Yes
MODPY_VERSION=		${MODPY_DEFAULT_VERSION_3}

TEST_DEPENDS=		devel/py-nose${MODPY_FLAVOR}

post-install:
	${INSTALL_MAN} ${WRKSRC}/man/asciinema.1 ${PREFIX}/man/man1/

do-test:
	cd ${WRKSRC} && nosetests${MODPY_BIN_SUFFIX}

.include <bsd.port.mk>
