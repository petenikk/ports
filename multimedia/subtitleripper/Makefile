COMMENT=	subtitle ripper, used with transcode

DISTNAME=	subtitleripper-0.3-4
PKGNAME=	subtitleripper-0.3.4
REVISION=	1
EXTRACT_SUFX=	.tgz
CATEGORIES=	multimedia
FIX_EXTRACT_PERMISSIONS=Yes

HOMEPAGE=	http://subtitleripper.sourceforge.net/

# GPL
PERMIT_PACKAGE=	Yes

SITES=		${SITE_SOURCEFORGE:=subtitleripper/}

WANTLIB=	c m z png netpbm

USE_GMAKE=	Yes
LIB_DEPENDS=	graphics/png \
		graphics/netpbm
RUN_DEPENDS=	multimedia/transcode

WRKDIST=        ${WRKDIR}/subtitleripper
NO_TEST=	Yes

pre-configure:
	@perl -pi -e 's,!!LOCALBASE!!,${LOCALBASE},g' \
		${WRKSRC}/Makefile

.include <bsd.port.mk>
