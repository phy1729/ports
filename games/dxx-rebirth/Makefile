# $OpenBSD: Makefile,v 1.4 2019/01/06 21:26:03 thfr Exp $

V =		0.60
COMMENT =	source port of Descent, a 6-degrees-of-freedom shooter
DISTNAME =	dxx-rebirth_v${V}-weekly-11-08-17-src
PKGNAME =	dxx-rebirth-${V}
CATEGORIES =	games x11
REVISION =	2

HOMEPAGE =	http://www.dxx-rebirth.com/
MAINTAINER =	Thomas Frohwein <thfr@openbsd.org>

# GPLv3 with special exception for Parallax license
PERMIT_PACKAGE_CDROM =	selling explicitly prohibited
PERMIT_PACKAGE_FTP =	Yes

WANTLIB += ${COMPILER_LIBCXX} GL GLU SDL SDL_mixer c m physfs

MASTER_SITES =	http://www.dxx-rebirth.com/download/dxx/user/afuturepilot/

# C++14
COMPILER =	base-clang ports-gcc base-gcc

MODULES =	devel/scons
MODSCONS_ENV =	CPPFLAGS="-I${LOCALBASE}/include" \
		CXXFLAGS="${CXXFLAGS}" \
		LINKFLAGS="-L${LOCALBASE}/lib"
MODSCONS_FLAGS =	ignore_unknown_variables=1 verbosebuild=1

LIB_DEPENDS =	devel/physfs \
		devel/sdl \
		devel/sdl-mixer

NO_TEST =	Yes

WRKDIST =	${WRKDIR}/dxx-rebirth_v${V}-weekly-src

.include <bsd.port.mk>
