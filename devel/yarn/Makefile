COMMENT =	fast, reliable, and secure dependency management for node.js

V =		v1.22.18
DISTNAME =	yarn-${V}
PKGNAME =	yarn-${V:S/v//}
REVISION =	0

CATEGORIES =	devel

HOMEPAGE =	https://yarnpkg.com/lang/en/

# BSD
PERMIT_PACKAGE =	Yes

SITES =			https://github.com/yarnpkg/yarn/releases/download/${V}/

RUN_DEPENDS =		lang/node

NO_BUILD =		Yes
NO_TEST =		Yes

# yarn relies on process.execPath to determine where node is. This doesn't
# work as expected on OpenBSD as it will always be relative to what was
# called. Because of this, we explicitly patch yarn to know where the node
# binary is.
pre-configure:
	${SUBST_CMD} ${WRKSRC}/lib/cli.js

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/bin/* ${PREFIX}/bin/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/
	${INSTALL_DATA} ${WRKSRC}/lib/* ${PREFIX}/lib/
	rm ${PREFIX}/lib/*.beforesubst ${PREFIX}/lib/*${PATCHORIG}

.include <bsd.port.mk>
