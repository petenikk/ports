COMMENT =	background setter for Wayland

DISTNAME =	swaybg-1.2.0
SITES =		https://github.com/swaywm/swaybg/releases/download/v1.2.0/

CATEGORIES =	wayland

# MIT
PERMIT_PACKAGE = Yes

MODULES =	devel/meson

BUILD_DEPENDS =	wayland/wayland-protocols \
		textproc/scdoc

LIB_DEPENDS =	graphics/gdk-pixbuf2 \
		graphics/cairo \
		wayland/wayland

WANTLIB += c cairo gdk_pixbuf-2.0 gobject-2.0 wayland-client

DEBUG_PACKAGES =${BUILD_PACKAGES}

.include <bsd.port.mk>
