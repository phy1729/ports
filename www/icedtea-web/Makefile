# $OpenBSD: Makefile,v 1.29 2018/07/05 16:55:42 giovanni Exp $

COMMENT =	Java web start runtime
DISTNAME =	icedtea-web-1.6.2
REVISION =	6
CATEGORIES =	www

MAINTAINER =	Giovanni Bechis <giovanni@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	http://icedtea.classpath.org/download/source/
HOMEPAGE =	http://icedtea.classpath.org/wiki/IcedTea-Web

CONFIGURE_STYLE =	gnu
CONFIGURE_ENV =		BIN_BASH=${LOCALBASE}/bin/bash
CONFIGURE_ARGS =	--with-jdk-home=${JAVA_HOME} \
			--disable-docs \
			--disable-plugin

MODULES =	java

MODJAVA_VER=	1.8

#build system does horrible things with bash
RUN_DEPENDS =	shells/bash \
		devel/desktop-file-utils
BUILD_DEPENDS =	${RUN_DEPENDS} \
		archivers/zip

USE_GMAKE =	Yes

post-patch:
	${SUBST_CMD} ${WRKSRC}/launcher/launchers.in

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/applications
	${INSTALL_DATA} ${WRKSRC}/*.desktop ${PREFIX}/share/applications/

.include <bsd.port.mk>
