# $OpenBSD: Makefile,v 1.7 2019/02/10 12:56:07 sthen Exp $

COMMENT =	PerlIO layer that adds read & write timeout to a handle

DISTNAME =	PerlIO-via-Timeout-0.32
REVISION =	0
CATEGORIES =	devel

MAINTAINER =	Benoit Lecocq <benoit@openbsd.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		cpan
PKG_ARCH =		*

RUN_DEPENDS =		devel/p5-Time-Out
TEST_DEPENDS =		net/p5-Test-TCP

.include <bsd.port.mk>
