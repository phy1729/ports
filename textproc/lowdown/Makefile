# $OpenBSD: Makefile,v 1.16 2018/12/28 08:22:48 anton Exp $

COMMENT =	simple markdown translator
DISTNAME =	lowdown-0.4.2
CATEGORIES =	textproc

HOMEPAGE =	https://kristaps.bsd.lv/lowdown/
MAINTAINER =	Bryan Vyhmeister <bryan@bsdjournal.net>

# ISC
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	https://kristaps.bsd.lv/lowdown/snapshots/

# uses pledge()
WANTLIB +=	c m

CONFIGURE_STYLE =	simple
CONFIGURE_ARGS =	PREFIX="${PREFIX}"

ALL_TARGET =	lowdown

NO_TEST =	Yes

.include <bsd.port.mk>
