# $OpenBSD: Makefile,v 1.43 2018/11/15 21:12:45 bcallah Exp $

COMMENT=	spell checker designed to eventually replace Ispell

DISTNAME=	aspell-0.60.6.1
REVISION=	8
SHARED_LIBS +=  aspell               17.0     # .16.4
SHARED_LIBS +=  pspell               17.0     # .16.4
DIST_SUBDIR=	aspell
CATEGORIES=	textproc

DIST_EN=	aspell6-en-7.1-0

MASTER_SITES0=	${MASTER_SITE_GNU:=aspell/}
MASTER_SITES1=	${MASTER_SITE_GNU:=aspell/dict/en/}

DISTFILES=	${DISTNAME}${EXTRACT_SUFX}:0 \
		${DIST_EN}.tar.bz2:1

HOMEPAGE=	http://aspell.net/

# LGPLv2.1
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=		c iconv intl m ncursesw pthread ${COMPILER_LIBCXX}

COMPILER =		base-clang ports-gcc base-gcc

LIB_DEPENDS=		devel/gettext

CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"
CONFIGURE_ARGS+=	--enable-static \
			--enable-curses=ncursesw \
			--enable-dict-dir=${PREFIX}/share/aspell \
			--enable-docdir=${PREFIX}/share/doc/aspell

post-build:
	cd ${WRKDIR}/${DIST_EN} && \
		cp ${WRKSRC}/data/* . && \
		LD_LIBRARY_PATH=${WRKBUILD}/.libs ./configure --vars \
			ASPELL=${WRKBUILD}/aspell \
			ASPELL_FLAGS="--local-data-dir=${WRKDIR}/${DIST_EN}" \
			PREZIP=${WRKBUILD}/prezip-bin && \
		${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} ${MAKE_FLAGS} \
			LD_LIBRARY_PATH=${WRKBUILD}/.libs

post-install:
	cd ${WRKDIR}/${DIST_EN} && \
		${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} \
			dictdir=${PREFIX}/share/aspell \
			datadir=${PREFIX}/lib/aspell \
			${INSTALL_TARGET}

.include <bsd.port.mk>
