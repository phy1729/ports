# $OpenBSD: Makefile,v 1.15 2018/11/12 18:49:48 naddy Exp $

COMMENT =	MAME port with advanced video support for monitors and TVs

V =		3.9
DISTNAME =	advancemame-$V
REVISION =	0

CATEGORIES =	emulators games

HOMEPAGE =	https://www.advancemame.it/

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

# GPLv2+ and MAME License
PERMIT_PACKAGE_CDROM =	unclear license
PERMIT_PACKAGE_FTP =	unclear license
PERMIT_DISTFILES_FTP =	unclear license

WANTLIB +=	SDL2 c expat freetype m pthread z

MASTER_SITES =	https://github.com/amadvance/advancemame/releases/download/v$V/

LIB_DEPENDS =	devel/sdl2

CONFIGURE_STYLE = gnu
CONFIGURE_ARGS = --disable-asm

USE_GMAKE =	Yes

post-patch:
	@sed -i 's,@@,@,' ${WRKSRC}/Makefile.in

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/obj/mame/generic/blend/advmame ${PREFIX}/bin
	${INSTALL_PROGRAM} ${WRKSRC}/obj/mess/generic/blend/advmess ${PREFIX}/bin
	${INSTALL_DATA} ${WRKSRC}/doc/advmame.1 ${PREFIX}/man/man1
	${INSTALL_DATA} ${WRKSRC}/doc/advmame.1 ${PREFIX}/man/man1/advmess.1
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/advancemame
	${INSTALL_DATA} ${WRKSRC}/doc/advmame.txt ${PREFIX}/share/doc/advancemame

.include <bsd.port.mk>
