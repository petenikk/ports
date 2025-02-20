COMMENT =	command-driven interactive function plotting program

V =		5.4
PATCHLEVEL =	8
DISTNAME =	gnuplot-${V}.${PATCHLEVEL}
CATEGORIES =	math graphics
SITES =		${SITE_SOURCEFORGE:=gnuplot/}

HOMEPAGE =	http://www.gnuplot.info/

MAINTAINER =	Paul Irofti <paul@irofti.net>

# see Copyright in source
# http://gnuplot.cvs.sourceforge.net/gnuplot/gnuplot/Copyright
PERMIT_PACKAGE =	Yes

WANTLIB += c cerf m curses ereadline ${COMPILER_LIBCXX} z

COMPILER =		base-clang ports-gcc base-gcc

LIB_DEPENDS +=	devel/readline \
		math/libcerf

FLAVORS =	no_cairo no_x11
FLAVOR ?=

CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS =	--without-linux-vga \
			--without-latex \
			--without-tutorial \
			--with-readline=${LOCALBASE} \
			--disable-wxwidgets \
			--with-qt=no \
			--without-lua \
			--without-pdf
CONFIGURE_ENV =		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

USE_GMAKE =		Yes

FAKE_FLAGS =		appdefaultdir="${PREFIX}/lib/X11/app-defaults/"

TEST_IS_INTERACTIVE =	x11

SUBST_VARS =	V

.if ${FLAVOR:Mno_x11}
CONFIGURE_ARGS += --without-x \
		  --without-gd
.else
LIB_DEPENDS +=	graphics/gd
WANTLIB +=	X11 gd
CONFIGURE_ARGS += --with-x
.endif

.if ${FLAVOR:Mno_cairo} || ${FLAVOR:Mno_x11}
CONFIGURE_ARGS += --without-cairo
.else
LIB_DEPENDS +=	converters/libiconv \
		devel/gettext,-runtime \
		devel/pango \
		graphics/cairo
WANTLIB +=	cairo gobject-2.0 glib-2.0 intl pango-1.0 pangocairo-1.0 harfbuzz
.endif

.include <bsd.port.mk>
