COMMENT =	free font editor for TTF, EOT, and SVG fonts

DISTNAME =	birdfont-2.29.4
REVISION =	7
CATEGORIES =	graphics print

SHARED_LIBS +=	birdfont			17.0 # 2.11.7
SHARED_LIBS +=	birdgems			17.0 # 2.11.7

HOMEPAGE =	https://birdfont.org/

# GPLv3+
PERMIT_PACKAGE =	Yes


SITES =		https://birdfont.org/releases/
EXTRACT_SUFX =	.tar.xz

WANTLIB += atk-1.0 c cairo cairo-gobject fontconfig freetype gdk-3
WANTLIB += gdk_pixbuf-2.0 gee-0.8 gio-2.0 glib-2.0 gobject-2.0
WANTLIB += gtk-3 intl javascriptcoregtk-4.0 m notify pango-1.0
WANTLIB += pangocairo-1.0 soup-2.4 sqlite3 webkit2gtk-4.0 xmlbird
WANTLIB += z harfbuzz gmodule-2.0 pthread

MODULES =	lang/python

MODPY_ADJ_FILES =	configure install.py build.py

BUILD_DEPENDS =	devel/gettext,-tools \
		lang/vala

LIB_DEPENDS =	devel/libgee \
		devel/libnotify \
		textproc/libxmlbird \
		www/webkitgtk4

RUN_DEPENDS =	devel/desktop-file-utils \
		fonts/roboto-fonts \
		misc/shared-mime-info \
		x11/gtk+4,-guic

CONFIGURE_STYLE =	simple
CONFIGURE_ARGS =	-c "${CC}"

NO_TEST =	Yes

SUBST_VARS +=	DESTDIR

pre-configure:
	sed -i "s,bash,sh,g" ${WRKSRC}/*.sh ${WRKSRC}/scripts/run.py
	${SUBST_CMD} ${WRKSRC}/configure ${WRKSRC}/install.py \
		${WRKSRC}/dodo.py ${WRKSRC}/scripts/version.py

do-build:
	cd ${WRKSRC} && ./build.py

do-install:
	cd ${WRKSRC} && ./install.py --nogzip=1
	# Remove bundled font files
	rm ${PREFIX}/share/birdfont/*.ttf

.include <bsd.port.mk>
