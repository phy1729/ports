# $OpenBSD: Makefile,v 1.4 2019/03/18 10:38:40 jung Exp $

COMMENT =		parser/generator of iCalendar files

MODPY_EGG_VERSION =	4.0.3
DISTNAME =		icalendar-${MODPY_EGG_VERSION}
PKGNAME =		py-icalendar-${MODPY_EGG_VERSION}

CATEGORIES =		devel

HOMEPAGE =		https://icalendar.readthedocs.org

MAINTAINER =		Joerg Jung <jung@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python

MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes

RUN_DEPENDS =		devel/py-dateutil${MODPY_FLAVOR} \
			devel/py-tz${MODPY_FLAVOR}
TEST_DEPENDS =		${RUN_DEPENDS} \
			devel/py-coverage${MODPY_FLAVOR} \
			devel/py-hypothesis${MODPY_FLAVOR} \
			devel/py-six${MODPY_FLAVOR}

FLAVORS =		python3
FLAVOR ?=

post-install:
	for i in ${PREFIX}/bin/*; do \
		mv $${i} $${i}${MODPY_BIN_SUFFIX} ;\
	done

.include <bsd.port.mk>
