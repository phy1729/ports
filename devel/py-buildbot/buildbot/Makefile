# $OpenBSD: Makefile,v 1.7 2018/09/06 18:34:26 landry Exp $

COMMENT =	continuous integration framework

DISTNAME =	buildbot-${MODPY_EGG_VERSION}
PKGNAME =	${DISTNAME}

RUN_DEPENDS =	databases/py-sqlalchemy${MODPY_FLAVOR} \
		databases/py-sqlalchemy-migrate${MODPY_FLAVOR} \
		devel/py-buildbot/www \
		devel/py-dateutil${MODPY_FLAVOR} \
		devel/py-twisted${MODPY_FLAVOR} \
		devel/py-future${MODPY_FLAVOR} \
		devel/py-txaio${MODPY_FLAVOR} \
		www/py-autobahn${MODPY_FLAVOR} \
		www/py-jwt${MODPY_FLAVOR} \
		www/py-jinja2${MODPY_FLAVOR}

NO_TEST =	Yes
#TEST_DEPENDS =	${RUN_DEPENDS} \
#			devel/py-mock${MODPY_FLAVOR}
# also needs treq, pyjade ?

UPDATE_PLIST_ARGS+=-i MODPY_PY_PREFIX

HOMEDIR =		/var/buildbot

SUBST_VARS +=		HOMEDIR

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/buildbot
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/buildbot
	${INSTALL_DATA} ${WRKSRC}/README.rst ${PREFIX}/share/doc/buildbot
	${INSTALL_DATA} ${WRKSRC}/docs/examples/*.cfg \
	    ${PREFIX}/share/examples/buildbot
	${INSTALL_MAN} ${WRKSRC}/docs/buildbot.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
