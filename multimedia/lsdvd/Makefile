COMMENT=		print information about the content and structure of a DVD

DISTNAME=		lsdvd-0.17
CATEGORIES=		multimedia

HOMEPAGE=		http://lsdvd.sourceforge.net/

# GPLv2
PERMIT_PACKAGE=	Yes

WANTLIB += c dvdread

SITES=			${SITE_SOURCEFORGE:=lsdvd/}

LIB_DEPENDS=		devel/libdvdread

CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

.include <bsd.port.mk>
