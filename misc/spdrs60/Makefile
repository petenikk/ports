COMMENT =	graphical SRCP client to control a digital model railway

DISTNAME =	spdrs60-0.6.5
CATEGORIES =	misc x11

HOMEPAGE =	http://spdrs60.sourceforge.net/
SITES =		${SITE_SOURCEFORGE:=spdrs60/}

MAINTAINER =	Sebastian Reitenbach <sebastia@openbsd.org>

# GPLv2
PERMIT_PACKAGE =		Yes

MODULES =		x11/qt5
WANTLIB += c m pthread Qt5Core Qt5Gui Qt5Network Qt5Widgets
WANTLIB += ${COMPILER_LIBCXX}

CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS +=	${MODQT_CONFIGURE_ARGS} --disable-html-doc \
			--enable-qt5
CONFIGURE_ENV +=	CXXFLAGS="${CXXFLAGS} -std=c++11" \
			LDFLAGS="-L${LOCALBASE}/lib -L${X11BASE}/lib"

.include <bsd.port.mk>
