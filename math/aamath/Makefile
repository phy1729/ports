# $OpenBSD: Makefile,v 1.18 2018/10/24 14:28:07 sthen Exp $

COMMENT=		ASCII art mathematics

DISTNAME=		aamath-0.3
REVISION =		4
CATEGORIES=		math

HOMEPAGE=		http://fuse.superglue.se/aamath/

MAINTAINER=		Matthias Kilian <kili@openbsd.org>

# GPL
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		http://openbsd.dead-parrot.de/distfiles/

WANTLIB=		c m ${COMPILER_LIBCXX} termcap readline

COMPILER =		base-clang ports-gcc base-gcc

NO_TEST=		Yes
WRKDIST=		${WRKDIR}/aamath
ALL_TARGET=
MAKE_FLAGS=		CXX="${CXX}" LD="${CXX}"

do-install:
	${INSTALL_PROGRAM} ${WRKDIST}/aamath ${PREFIX}/bin
	${INSTALL_MAN} ${WRKDIST}/aamath.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
