# $OpenBSD: Makefile,v 1.3 2019/03/08 20:00:48 cwen Exp $

COMMENT =	information about LXQt and the system its running on

VERSION =	0.13.0

NAME =		lxqt-about
DISTNAME =	${NAME}-${VERSION}
REVISION =	0

WANTLIB += ${COMPILER_LIBCXX} KF5WindowSystem Qt5Core Qt5DBus
WANTLIB += Qt5Gui Qt5Svg Qt5Widgets Qt5X11Extras Qt5Xdg Qt5XdgIconLoader
WANTLIB += Qt5Xml c lxqt m

LIB_DEPENDS +=		x11/lxqt/liblxqt

BUILD_DEPENDS +=	x11/lxqt/build-tools

RUN_DEPENDS +=		devel/desktop-file-utils \
			x11/lxqt/l10n,-about

CONFIGURE_ARGS +=	-DPULL_TRANSLATIONS:BOOL=OFF

.include <bsd.port.mk>
