COMMENT=	object-oriented SGML parser

DISTNAME=	OpenSP-1.5.2
PKGNAME=	${DISTNAME:L}
CATEGORIES=	textproc
REVISION=	4

SITES=		${SITE_SOURCEFORGE:=openjade/}

SHARED_LIBS=	osp 0.0 # .4.0

HOMEPAGE=	http://openjade.sourceforge.net/

# BSD
PERMIT_PACKAGE=	Yes

WANTLIB=	c iconv intl m pthread ${COMPILER_LIBCXX}

MODULES=	textproc/intltool

COMPILER =		base-clang ports-gcc base-gcc

LIB_DEPENDS=	devel/gettext,-runtime
USE_GMAKE=	Yes
CONFIGURE_STYLE=gnu
CONFIGURE_ARGS=	--with-libiconv-prefix=${LOCALBASE} \
		--with-libintl-prefix=${LOCALBASE}

BUILD_DEPENDS +=	textproc/xmlto \
			textproc/docbook

post-install:
	mv ${PREFIX}/share/doc/{OpenSP,opensp}

.include <bsd.port.mk>
