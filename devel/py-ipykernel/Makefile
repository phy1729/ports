# $OpenBSD: Makefile,v 1.7 2019/01/04 22:19:57 mariani Exp $

COMMENT =		IPython kernel for Jupyter

MODPY_EGG_VERSION =	4.10.0
DISTNAME =		ipykernel-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}

PORTROACH=		limit:^4

CATEGORIES =		devel

HOMEPAGE =		https://ipython.org/

MAINTAINER =		Elias M. Mariani <marianielias@gmail.com>

RUN_DEPENDS +=		devel/py-jupyter_client${MODPY_FLAVOR} \
			devel/py-traitlets${MODPY_FLAVOR}>=4.1.0 \
			www/py-tornado${MODPY_FLAVOR}>=4.0 \
			devel/ipython${MODPY_FLAVOR}>=4.0.0

TEST_DEPENDS =		${RUN_DEPENDS} \
			devel/py-nose${MODPY_FLAVOR} \
			devel/py-nose-warnings-filters${MODPY_FLAVOR} \
			devel/py-test${MODPY_FLAVOR} \
			devel/py-test-cov${MODPY_FLAVOR} \
			graphics/py-matplotlib${MODPY_FLAVOR} \
			math/py-numpy${MODPY_FLAVOR}

# BSD
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python
MODPY_PI =		Yes

FLAVORS =		python3
FLAVOR ?=

.if !${FLAVOR:Mpython3}
TEST_DEPENDS +=		devel/py-mock
.endif

do-test:
	cd ${WRKSRC} && ${LOCALBASE}/bin/nosetests${MODPY_BIN_SUFFIX} ipykernel

.include <bsd.port.mk>
