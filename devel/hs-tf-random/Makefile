# $OpenBSD: Makefile,v 1.6 2018/01/22 21:43:45 kili Exp $

COMMENT =		high-quality splittable PRNG

# Dependency of meta/haskell-platform.
# Please do *not* update without thinking.
PORTROACH =		ignore:1

DISTNAME =		tf-random-0.5
REVISION =		3
CATEGORIES =		devel

MAINTAINER =		Matthias Kilian <kili@openbsd.org>

# BSD3
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ghc

MODGHC_BUILD =		cabal hackage haddock register

MODGHC_PACKAGE_KEY =	ABwehMmciu8CuAFbHLp6To

BUILD_DEPENDS =		${RUN_DEPENDS}
RUN_DEPENDS =		devel/hs-primitive>=0.3 \
			devel/hs-random

.include <bsd.port.mk>
