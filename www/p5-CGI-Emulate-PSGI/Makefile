# $OpenBSD: Makefile,v 1.7 2017/01/24 02:36:03 afresh1 Exp $

COMMENT =	PSGI adapter for CGI

MODULES =	cpan
PKG_ARCH =	*
DISTNAME =	CGI-Emulate-PSGI-0.22
CATEGORIES =	www

MAINTAINER =	Andrew Fresh <afresh1@openbsd.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

RUN_DEPENDS =	www/p5-HTTP-Message
TEST_DEPENDS =	devel/p5-Test-Requires>=0.08

# Additional dependencies to avoid warnings and skipping test
MAKE_ENV =	AUTHOR_TESTING=1
TEST_DEPENDS +=	www/p5-CGI \
		www/p5-Plack \
		devel/p5-Test-Pod

.include <bsd.port.mk>
