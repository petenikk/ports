COMMENT=		advanced menu for MATE

GH_COMMIT=		61a995e25948015a4f6d86e12cf6141a3b729ce7
GH_ACCOUNT=		rnagy
GH_PROJECT=		mate-menu
DISTNAME=		mate-menu-advanced-20.04.1
REVISION=		4

CATEGORIES=		x11

# GPLv2
PERMIT_PACKAGE=		Yes

MODULES=		devel/dconf \
			lang/python \
			x11/gnome

MODGNOME_TOOLS=		gtk-update-icon-cache \
			gobject-introspection

MODPY_SETUPTOOLS=	Yes

BUILD_DEPENDS=		devel/gettext,-tools \
			devel/py-distutils-extra${MODPY_FLAVOR}

RUN_DEPENDS=		devel/py-gobject3${MODPY_FLAVOR} \
			devel/py-setproctitle${MODPY_FLAVOR} \
			x11/mate/panel \
			x11/py-xlib${MODPY_FLAVOR} \
			x11/gtk+3

.include <bsd.port.mk>
