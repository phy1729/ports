# $OpenBSD: Makefile,v 1.5 2019/03/24 11:57:04 rsadowski Exp $

COMMENT =	Hex Editor
VERSION =	0.25.4
DISTNAME =	okteta-${VERSION}
CATEGORIES =	editors
REVISION =	0

EPOCH =		0


SHARED_LIBS +=  kasten3controllers        0.0 # 0.3
SHARED_LIBS +=  kasten3core               0.0 # 0.3
SHARED_LIBS +=  kasten3gui                0.0 # 0.3
SHARED_LIBS +=  kasten3okteta1controllers 0.0 # 0.3
SHARED_LIBS +=  kasten3okteta1core        0.0 # 0.3
SHARED_LIBS +=  kasten3okteta1gui         0.0 # 0.3
SHARED_LIBS +=  okteta2core               0.0 # 0.9
SHARED_LIBS +=  okteta2gui                0.0 # 0.9

WANTLIB += ${COMPILER_LIBCXX} KF5Attica KF5Auth KF5Bookmarks KF5Codecs
WANTLIB += KF5Completion KF5ConfigCore KF5ConfigGui KF5ConfigWidgets
WANTLIB += KF5CoreAddons KF5Crash KF5DBusAddons KF5I18n KF5IconThemes
WANTLIB += KF5ItemViews KF5JobWidgets KF5KCMUtils KF5KIOCore KF5KIOFileWidgets
WANTLIB += KF5KIOWidgets KF5NewStuff KF5NewStuffCore KF5Parts
WANTLIB += KF5Service KF5Solid KF5SonnetUi KF5TextWidgets KF5WidgetsAddons
WANTLIB += KF5XmlGui Qt5Concurrent Qt5Core Qt5DBus Qt5Gui Qt5Network
WANTLIB += Qt5PrintSupport Qt5Qml Qt5Script Qt5Widgets Qt5Xml
WANTLIB += c m qca-qt5

MASTER_SITES =	${MASTER_SITE_KDE:=stable/okteta/${VERSION}/src/}

MODKDE5_DESKTOP_FILE = yes
MODKDE5_ICON_CACHE = yes
MODKDE5_TRANSLATIONS = yes
MODKDE5_DOCS = yes

MODULES +=	x11/kde-applications

RUN_DEPENDS +=	misc/shared-mime-info

LIB_DEPENDS +=	devel/kf5/kbookmarks \
		devel/kf5/kcodecs \
		devel/kf5/kcompletion \
		devel/kf5/kconfigwidgets \
		devel/kf5/kdbusaddons \
		devel/kf5/kiconthemes \
		devel/kf5/ki18n \
		devel/kf5/kcmutils \
		devel/kf5/knewstuff \
		devel/kf5/kparts \
		devel/kf5/kio \
		devel/kf5/kservice \
		devel/kf5/kwidgetsaddons \
		devel/kf5/kxmlgui \
		security/qca-qt5 \
		x11/qt5/qtscript \
		x11/qt5/qtdeclarative

TEST_IS_INTERACTIVE =	X11

.include <bsd.port.mk>
