COMMENT =		control-spec implementation for Tor

MODPY_EGG_VERSION =	22.0.0
DISTNAME =		txtorcon-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
REVISION =		1

HOMEPAGE =		https://txtorcon.readthedocs.org

CATEGORIES =		net

# MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_PI =		Yes
MODPY_PYBUILD =		setuptools

FLAVORS =		python3
FLAVOR =		python3

RUN_DEPENDS =		devel/py-automat${MODPY_FLAVOR} \
			devel/py-twisted${MODPY_FLAVOR}

post-install:
	mv ${PREFIX}/share/txtorcon/examples ${PREFIX}/share/examples/txtorcon
	mv ${PREFIX}/share/txtorcon ${PREFIX}/share/doc/txtorcon

.include <bsd.port.mk>
