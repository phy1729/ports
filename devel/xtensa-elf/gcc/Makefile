# $OpenBSD: Makefile,v 1.3 2018/10/27 05:48:32 bentley Exp $

COMMENT=	gcc for xtensa-elf cross-development

VERSION=	6.3.0
DISTNAME=	gcc-${VERSION}
PKGNAME=	${CONFIG}-gcc-${VERSION}
REVISION=	0

SUBST_VARS+=	VERSION

WANTLIB=	${COMPILER_LIBCXX} c gmp m mpc mpfr
DIST_SUBDIR=	gcc

MASTER_SITES= 	${MASTER_SITE_GCC:=releases/gcc-$(VERSION)/}

COMPILER =		base-clang ports-gcc base-gcc

BUILD_DEPENDS+=	devel/bison \
		devel/xtensa-elf/binutils

LIB_DEPENDS=	devel/mpfr \
		devel/libmpc

RUN_DEPENDS =	devel/xtensa-elf/binutils

CONFIGURE_ARGS+=--enable-languages=c \
		--with-newlib \
		--with-gmp="${LOCALBASE}" \
		--disable-libstdcxx-pch \
		--disable-libstdc__-v3 \
		--disable-libssp \
		--disable-libstdcxx \
		--disable-libcc1 \
		--disable-lto
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib"

SEPARATE_BUILD=	Yes
USE_GMAKE=	Yes
YACC=		bison

TEST_DEPENDS=devel/dejagnu

post-install:
	chown -R ${SHAREOWN}:${SHAREGRP} \
		${PREFIX}/lib/gcc/${CONFIG}/${VERSION}/

.include <bsd.port.mk>
