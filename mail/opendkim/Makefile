COMMENT=	library and milter for DKIM (Domain Keys Identified Mail)

DISTNAME=	opendkim-2.10.3
REVISION=	3

SHARED_LIBS +=	opendkim             0.0      # 10.3

CATEGORIES=	mail

HOMEPAGE=	http://www.opendkim.org/

# BSD, Sendmail
PERMIT_PACKAGE=	Yes

WANTLIB += c crypto milter pthread ssl

SITES=		${SITE_SOURCEFORGE:=opendkim/}

LIB_DEPENDS=	mail/sendmail,-libmilter

TEST_FLAGS=	COV_LIBADD=-pthread

SEPARATE_BUILD=	Yes
CONFIGURE_STYLE= gnu

CONFIGURE_ARGS=	--enable-replace_rules

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/opendkim/
	${INSTALL_DATA} ${WRKSRC}/opendkim/opendkim.conf.sample \
	    ${PREFIX}/share/examples/opendkim/

.include <bsd.port.mk>
