ONLY_FOR_ARCHS =	amd64 i386 powerpc powerpc64

COMMENT =		Plan 9 from user space

DISTNAME =		plan9port-20230913

GH_ACCOUNT =		9fans
GH_PROJECT =		plan9port
GH_COMMIT =		984c2824e3569479bace65bdaf9e78a2eb36dd58

CATEGORIES =		plan9

HOMEPAGE =		https://9fans.github.io/plan9port/

MAINTAINER =		Gleydson Soares <gsoares@openbsd.org>

# mostly MIT (see LICENSE)
# certain fonts may NOT be redistributed separately
PERMIT_PACKAGE =	Yes

WANTLIB =		X11 Xext c m pthread util fontconfig freetype z

WRKDIST =		${WRKDIR}/plan9port-${GH_COMMIT}

PLAN9 =			${PREFIX}/plan9

NO_TEST =		Yes

SUBST_VARS +=		CC
UPDATE_PLIST_ARGS += -i CC

pre-configure:
	${SUBST_CMD} ${WRKSRC}/INSTALL ${WRKSRC}/bin/{9c,9l}
	cd ${WRKSRC} && sed -i 's,#!/bin/bash,#!/bin/sh,' \
		bin/macedit

do-build:
	cd ${WRKSRC} && env CC9="${CC}" CCFLAGS="${CFLAGS}" NPROC=${MAKE_JOBS} ./INSTALL -b

do-install:
	rm -f ${WRKSRC}/.travis.yml
	cd ${WRKSRC} && sed -i 's#/usr/local#${TRUEPREFIX}#' \
		`cat lib/moveplan9.files`
	find ${WRKSRC} \( -name .gitignore -o -name .gitkeep -o \
		-name \*.orig -o -name \*.beforesubst \) -delete
	${INSTALL_DATA_DIR} ${PLAN9}
	cd ${WRKSRC} && pax -rw . ${PLAN9}
	cd ${PREFIX} && ln -s ../plan9/bin/9 bin/9

.include <bsd.port.mk>
