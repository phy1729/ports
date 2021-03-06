# $OpenBSD: Makefile,v 1.26 2018/10/17 14:15:56 sthen Exp $

COMMENT-main=	base classes for common PHP tasks
COMMENT-utils=	utilities for managing pear extensions

VERSION=	1.10.1
DISTNAME=	go-pear-${VERSION}
PKGNAME=	pear-${VERSION}
EXTRACT_SUFX=	.phar
EXTRACT_ONLY=
PKGNAME-main=	pear-${VERSION}
PKGNAME-utils=	pear-utils-${VERSION}
REVISION=	1
WRKDIST=	${WRKDIR}
CATEGORIES=	www devel

HOMEPAGE=	http://pear.php.net/
MASTER_SITES=	https://spacehopper.org/mirrors/

MAINTAINER=	Robert Nagy <robert@openbsd.org>

PERMIT_PACKAGE_CDROM=	Yes

MULTI_PACKAGES=		-main -utils

MODULES=		lang/php
BUILD_DEPENDS=		${_MODPHP_BUILD_DEPENDS}
RUN_DEPENDS-main=	www/pear,-utils

# Most of pear have to live in /var/www where apache is chroot'ed to.
PREFIX-main=	${VARBASE}/www
PREFIX-utils=	/usr/local

NO_TEST=	Yes

BUILD_DEPENDS=	devel/p5-Expect
SUBST_VARS=	MODPHP_BIN

do-extract:
	cp ${FULLDISTDIR}/${DISTFILES} ${WRKSRC}/go-pear.phar

do-build:
	cd ${WRKSRC}; perl ${FILESDIR}/run-go-pear ${WRKINST} ${PREFIX} ${MODPHP_BIN}

do-install:
	@find ${WRKINST}${PREFIX-main} -name "*.php" -exec perl -pi -e "s,${WRKINST},,g" {} \;
	@find ${WRKINST}${PREFIX-utils}/bin -type f -exec perl -pi -e "s,${WRKINST},,g" {} \;

	@for _f in patch-usr_local_bin_pear patch-usr_local_bin_peardev \
		patch-usr_local_bin_pecl patch-var_www_pear_lib_PEAR_Config_php; do \
		patch -d ${WRKINST} < ${FILESDIR}/$${_f}; done
	@find ${WRKINST}/usr/local/bin -type f -exec ${SUBST_CMD} {} \;
	@perl -pi -e "s,OPENBSD_PEAR_ROOT,'${PREFIX-main}/pear',g" \
		${WRKINST}${PREFIX-main}/pear/lib/PEAR/Config.php
	@touch ${WRKINST}${PREFIX-main}/pear/.lock
	@touch ${WRKINST}${PREFIX-main}/pear/lib/.lock
	@rm ${PREFIX}/bin/{pear,peardev,pecl}{.beforesubst,.orig}*
	@rmdir ${WRKINST}${PREFIX-main}/pear/{cfg,htdocs}

.include <bsd.port.mk>
