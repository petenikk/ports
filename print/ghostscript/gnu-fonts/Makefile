COMMENT=		35 standard PostScript fonts with Adobe name aliases

DISTNAME=		ghostscript-fonts-std-8.11
PKGNAME=		${DISTNAME:S,-std-,-,}
REVISION=		3
CATEGORIES=		x11 print fonts

HOMEPAGE=		http://www.cs.wisc.edu/~ghost/doc/cvs/Fonts.htm

# GPL
PERMIT_PACKAGE=	Yes

SITES=		${SITE_SOURCEFORGE:=ghostscript/}

WRKDIST=	${WRKDIR}
NO_BUILD=	Yes
NO_TEST=	Yes
PKG_ARCH=	*
FONTDIR=	${PREFIX}/share/fonts/ghostscript

do-install:
	${INSTALL_DATA_DIR} ${FONTDIR}
	${INSTALL_DATA} ${WRKDIST}/fonts/*.{afm,pfm,pfb} ${FONTDIR}
	${INSTALL_DATA} ${FILESDIR}/fonts.alias ${FONTDIR}/fonts.alias-gs

.include <bsd.port.mk>
