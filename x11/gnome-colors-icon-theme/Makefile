# $OpenBSD: Makefile,v 1.14 2018/07/09 15:09:38 ajacoutot Exp $

COMMENT =		complete, multi-colored suite of icons

V =			5.5.1
REVISION =		10
DISTNAME =		gnome-colors-${V}
PKGNAME =		gnome-colors-icon-theme-${V}
CATEGORIES =		x11

HOMEPAGE =		https://github.com/gnome-colors/gnome-colors
MASTER_SITES =		${MASTER_SITE_GOOGLECODE:=gnome-colors/}

# GPLv2 
PERMIT_PACKAGE_CDROM =	Yes

PKG_ARCH =		*
NO_BUILD =		Yes
NO_TEST =		Yes

RUN_DEPENDS =		x11/gtk+3,-guic

WRKDIST =		${WRKDIR}
ICONSDIR =		${PREFIX}/share/icons/

do-install:
	${INSTALL_DATA_DIR} ${ICONSDIR}
	cd ${WRKDIST} ; pax -rw gnome-* ${ICONSDIR}

.include <bsd.port.mk>
