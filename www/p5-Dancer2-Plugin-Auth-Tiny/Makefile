# $OpenBSD: Makefile,v 1.3 2016/03/20 19:57:16 naddy Exp $

COMMENT =		require logged-in user for specified routes

MODULES =		cpan
PKG_ARCH =		*
DISTNAME =		Dancer2-Plugin-Auth-Tiny-0.005
CATEGORIES =		www

MAINTAINER =		Cesare Gargano <gar@plusiagamma.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

RUN_DEPENDS =		www/p5-Dancer2>=0.154000

TEST_DEPENDS =		www/p5-HTTP-Cookies \
			www/p5-HTTP-Message \
			www/p5-Plack
 
.include <bsd.port.mk>
