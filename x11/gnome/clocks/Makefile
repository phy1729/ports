# $OpenBSD: Makefile,v 1.44 2019/01/06 12:50:29 ajacoutot Exp $

COMMENT=		clock application for GNOME

GNOME_PROJECT=		gnome-clocks
GNOME_VERSION=		3.30.1

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c cairo gdk-3 gdk_pixbuf-2.0 geoclue-2 geocode-glib
WANTLIB += gio-2.0 glib-2.0 gnome-desktop-3 gobject-2.0 gsound
WANTLIB += gtk-3 gweather-3 intl m

MODULES=		devel/dconf \
			devel/meson \
			x11/gnome

LIB_DEPENDS=		audio/gsound \
			geo/geocode-glib \
			x11/gnome/desktop \
			x11/gnome/libgweather

# geocoding.vala
BUILD_DEPENDS +=	geo/geoclue2
RUN_DEPENDS +=		geo/geoclue2

MODGNOME_TOOLS=		desktop-file-utils gtk-update-icon-cache vala yelp

.include <bsd.port.mk>
