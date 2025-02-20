COMMENT=		GObject Introspection

GNOME_VERSION=		1.78.1
GNOME_PROJECT=		gobject-introspection

CATEGORIES=		devel

SHARED_LIBS += girepository-1.0          3.2 # 1.0.0

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# Library: LGPLv2+
# Tools: GPLv2+
PERMIT_PACKAGE=		Yes

MODULES=		devel/meson \
			lang/python \
			x11/gnome

WANTLIB += c ffi gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 m

LIB_DEPENDS=		devel/glib2

BUILD_DEPENDS=		devel/bison \
			graphics/cairo \
			textproc/py-markdown${MODPY_FLAVOR} \
			www/py-mako${MODPY_FLAVOR}

RUN_DEPENDS=		graphics/cairo \
			textproc/py-markdown${MODPY_FLAVOR} \
			www/py-mako${MODPY_FLAVOR}

# g-ir-scanner uses distutils functions. these are overridden by setuptools
# if setuptools is present (see site-packages/distutils-precedence.pth);
# enforce a dependency to avoid the case where setuptools might be removed
# mid-run, causing g-ir-scanner to fail.
#
# could be removed if/when gobject-introspection stops using distutils;
# see https://gitlab.gnome.org/GNOME/gobject-introspection/-/issues/395
RUN_DEPENDS+=		devel/py-setuptools${MODPY_FLAVOR}

# XXX: tests/scanner/test_transformer.py fails otherwise
TEST_DEPENDS+=		textproc/gsed

.include <bsd.port.arch.mk>
.if !${PROPERTIES:Mlld}
# tools/g-ir-scanner doesn't respect LDFLAGS passed through CONFIGURE_ENV
MAKE_ENV=		LDFLAGS="-L${X11BASE}/lib -L${LOCALBASE}/lib"
.endif

# XXX: tidy-up some GNU-isms; see above.
pre-test:
	sed -i 's,\"sed ,\"gsed ,g' ${WRKSRC}/tests/scanner/test_transformer.py

.include <bsd.port.mk>
