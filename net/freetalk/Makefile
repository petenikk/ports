COMMENT=	console based Jabber client

DISTNAME=	freetalk-3.2
REVISION=	6

CATEGORIES=	net

HOMEPAGE=	https://www.gnu.org/software/freetalk/

# GPLv3
PERMIT_PACKAGE=	Yes

WANTLIB=	c glib-2.0 gmp iconv idn intl ltdl m curses pthread \
		readline ${COMPILER_LIBCXX} guile loudmouth-1>=3

COMPILER =	base-clang ports-gcc base-gcc

SITES=		${SITE_SAVANNAH:=freetalk/}

LIB_DEPENDS=	lang/guile \
		net/loudmouth

AUTOCONF_VERSION=	2.61
CONFIGURE_STYLE= autoconf no-autoheader
CONFIGURE_ENV=	LDFLAGS="-L${LOCALBASE}/lib" \
		CPPFLAGS="-I${LOCALBASE}/include"

FAKE_FLAGS=	Examplesdir=${PREFIX}/share/examples/freetalk/

.include <bsd.port.mk>
