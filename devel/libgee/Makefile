# $OpenBSD: Makefile,v 1.50 2018/02/12 11:40:57 ajacoutot Exp $

COMMENT=		GObject based collection library

GNOME_PROJECT=		libgee
GNOME_VERSION=		0.20.1

SHARED_LIBS +=  gee-0.8              3.1      # 8.1

CATEGORIES=		devel

MAINTAINER=		Jasper Lievisse Adriaanse <jasper@openbsd.org>, \
			Antoine Jacoutot <ajacoutot@openbsd.org>

# LGPLv2.1
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ffi gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 iconv
WANTLIB += intl pcre pthread z

MODULES=		x11/gnome

MODGNOME_TOOLS=		gobject-introspection vala

LIB_DEPENDS=		devel/glib2

CONFIGURE_STYLE=	gnu

.include <bsd.port.mk>
