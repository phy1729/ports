# $OpenBSD: Makefile,v 1.16 2019/03/13 21:28:22 rsadowski Exp $

COMMENT =	KDE file search and metadata handling framework
DISTNAME =	baloo-${VERSION}
PKGNAME =	kf5-${DISTNAME}
EPOCH =		0
REVISION =	1

SHARED_LIBS =   KF5Baloo                  2.1
SHARED_LIBS +=  KF5BalooXapian            2.1
SHARED_LIBS +=  KF5BalooEngine            0.1 # 5.46

WANTLIB += ${COMPILER_LIBCXX} KF5ConfigCore KF5CoreAddons KF5FileMetaData
WANTLIB += KF5I18n KF5Solid Qt5Core Qt5DBus Qt5Network Qt5Qml
WANTLIB += lmdb m

BUILD_DEPENDS =	devel/gettext-tools \
		devel/kf5/kidletime \
		devel/kf5/kio \
		devel/kf5/kcrash

RUN_DEPENDS =	devel/kf5/kidletime \
		devel/kf5/kio \
		devel/kf5/kcrash \
		x11/gtk+3,-guic

LIB_DEPENDS =	databases/lmdb \
		devel/kf5/kconfig \
		devel/kf5/kfilemetadata \
		devel/kf5/ki18n \
		devel/kf5/solid \
		devel/kf5/kcoreaddons \
		x11/qt5/qtdeclarative

.include <bsd.port.mk>
